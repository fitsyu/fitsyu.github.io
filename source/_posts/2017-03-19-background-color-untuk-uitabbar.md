---
title: Background Color Untuk UITabBar
date: 2017-03-19
tags: swift
thumbnail: "/images/bg tinted tabbar.png"
---

Ceritanya ingin memberikan warna background pas tabnya  di _select_. Namun sayangnya tidak ada property yang bernama _selection background tint_ yang bisa diset di storyboard ataupun di code. Yang ada malah property _selection indicator image_.


Lalu...
# Apa yang bisa dilakukan ?

## Memasang gambar polos sebagai background.
![](/images/tab selected bg color.png)

Karena yang ada property _selection indicator image_, jadi apa boleh buat.
Berikut hasil dari Tab Bar yang diberikan _selection indicator image_:


![](/images/bg color image too big.png)

> Gawat! Gambarnya terlalu besar!

## Memasang gambar polos dengan ukuran fix
Seperti yang sudah dilihat dengan memberikan _selection indicator image_. gambar nya ternyata tidak di _resize_secara internal  agar sesuai dengan ukuran tab  bar nya. :(

Dengan kata lain, gambarnya harus sudah fix _size_ nya.

Oke. Kalau begitu kita tinggal _resize_ gambarnya saja. Mudah. Tapi berapa _size_ nya??

> Good Question

Subclass UITabBarControllernya dan pada _viewDidLoad()_ kita masukkan kode berikut:

``` swift
	class BgColoredTabBarController: UITabBarController {
			override func viewDidLoad() {
					super.viewDidLoad()


					let width  = tabBar.frame.width / 4
					let height = tabBar.frame.height

					print("\(width)x\(height)")

			}
	}
```


Set custom class di storyboard dengan class yang baru dibuat. Lalu **CMD+R**.

Dapet! dan berikut outputnya:
**103.5x49.0** (_Menggunakan Simulator iPhone 7s_)

Dari informasi tersebut, kita _resize_ gambar yang tadi digunakan sebagai _selection indicator image_. Kemudian mengganti property _selection indicator image_ yang lama dengan yang sudah diresize ini.
**CMD+R** dan hasilnya:

![](/images/work with fixed size img.png)

Yeah!  berhasil juga.


Tapi,
- Bagaimana kalo jumlah tab nya berubah ?
- Bagaimana kalo harus mengganti warna ?
- Bagaimana ukurannya kalo di iPhone yang lain?

Pada akhirnya akan ada ketergantungan yang besar dengan image editor eksternal dan itu dapat memperlambat proses _development_.

Kita kan _coder_ kenapa gak buat saja _code_ nya.

Yaitu beberapa baris _code_  yang dengan parameter warna saja dapat membuat sebuah objek gambar polos dengan warna yang ditentukan sesuai dengan ukuran tab yang sedang digunakan.

## Biarkan semuanya dibuat dengan _code_


``` swift
	extension UITabBarController {
			func setBarSelectedTintColor(_ color: UIColor) {
					// determine the size
					let w = self.tabBar.frame.width / CGFloat(self.tabBar.items!.count)
					let h = self.tabBar.frame.height
					let size = CGSize(width: w, height: h)

					// make image
					UIGraphicsBeginImageContextWithOptions(size, false, 0)
					color.setFill()
					UIRectFill(CGRect(x:0, y:0, width:size.width, height:size.height))
					let image = UIGraphicsGetImageFromCurrentImageContext()
					UIGraphicsEndImageContext()

					self.tabBar.selectionIndicatorImage = image
			}
	}
```

Contoh cara pakenya:

``` swift
    setBarSelectedTintColor( UIColor.black )

```

Khasiatnya:

![](/images/bg tinted tabbar.png)
# Demikian

Mudah-mudahan berguna. Thanks!

> ***Bye!***

![bye](/images/bye.gif)
