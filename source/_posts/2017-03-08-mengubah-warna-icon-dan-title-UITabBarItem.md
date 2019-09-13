---
title: Mengubah warna icon dan title UITabBarItem
date: 2017-03-08
tags: swift
---

Tidak semua hal dapat disetting dari storyboard. Salah satunya adalah warna icon dan title nya UITabBarItem. Secara default warna icon dan title mengikuti template. Namun sering kali apa yang diberikan oleh template bukan lah yang kita inginkan.

Sebelumnya yang harus diketahui adalah UITabBarItem punya dua _state_  (keadaan):
- **Selected**

Yaitu ketika user memilih tab

- **Unselected**

Yaitu ketika tab tidak dipilih


## Subclass UITabBarController

Marilah kita mulai dengan membuat TabBarController baru yang diturunkan dari UITabBarController bawaan Cocoa.

``` swift
class MyCustomTabBarController: UITabBarController
```


## Override fungsi viewWillAppear

``` swift
override func viewWillAppear()
```

**viewWillAppear** adalah fungsi yang dipanggil ketika sebuah view controller sudah dimuat ke dalam memory ( setelah **viewDidLoad** )

> Kenapa bukan di viewDidLoad ?

Karena di Swift 3 dan Xcode 8 ( yang sedang dipakai saat post ini ditulis ) setelah saya coba di viewDidLoad tabBarItem nya tidak berubah. Tapi di Swift 2 dan Xcode 7, kode ini berjalan di **viewDidLoad**






### Icon
#### Menyetel warna icon ketika selected

Membuat icon menjadi apa adanya tidak menggunakan template saat dipilih.

``` swift
item.selectedImage  = item.selectedImage?.withRenderingMode(.alwaysOriginal)
```



#### Menyetel warna icon ketika unselected

Membuat icon menjadi apa adanya tidak menggunakan template saat tidak dipilih.

``` swift
item.image  = item.image?.withRenderingMode(.alwaysOriginal)
```

### Title
#### Menyetel warna title ketika selected

Membuat agar warna title menjadi putih saat dipilih

``` swift
item.setTitleTextAttributes([NSForegroundColorAttributeName: UIColor.white ], for: .selected)
 ```

#### Menyetel warna title ketika unselected

Membuat agar warna title menjadi merah saat tidak dipilih.

``` swift
item.setTitleTextAttributes([NSForegroundColorAttributeName: UIColor.red ], for: .normal)
```




## Seluruhnya

``` swift

    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)

        // Loop untuk semua item di tab
        for item in self.tabBar.items!  {

            // Tab Icon
            item.selectedImage  = item.selectedImage?.withRenderingMode(.alwaysOriginal)
            item.image          = item.image?.withRenderingMode(.alwaysOriginal)

            // Tab Title
            item.setTitleTextAttributes([NSForegroundColorAttributeName: UIColor.white ], for: .selected)
            item.setTitleTextAttributes([NSForegroundColorAttributeName: UIColor.red], for: .normal)

        }
    }
```

## Terakhir
Buka storyboard tempat UITabBarController yang lama berada dan ganti class dari UITabBarController menjadi MyCustomTabBarController pada tab identity.


## Demikian
_Terima kasih! Semoga berguna! Sampai Jumpa!_
