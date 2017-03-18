---
title: Padding Untuk LeftView atau RightView UITextField
layout: post
---

Bila anda memberikan view untuk LeftView atau RightView pada UITextField, anda akan lihat bahwa view tersebut terlalu mepet ke pinggir UITextField.

	txOrgAirport.leftView = UIImageView(image: #imageLiteral(resourceName: "icon_location"))
	txOrgAirport.leftViewMode = .always

![too close](/images/left view that too close too edge.png)

# beberapa pendekatan
Saya udah coba memberikan auto layout namun tak berhasil.

Saya juga mencoba mengedit iconnya di GIMP dan memberikan padding manual :(. Walaupun ini berhasil tapi sangat terasa melelahkan bila banyak UITextField yang perlu diberi icon.

Saya juga mencoba mengubah **x** pada frame view nya, seperti berikut:

	let iconView = UIImageView(frame: CGRect(x: 8, y: 0, width: 20, height: 20))
	iconView.image = icon_location
	
Tetap tidak berhasil. 
> Yess!

Lalu saya coba membungkus ImageView di dalam View biasa. View yang diluar saya berikan width lebih lebar sesuai jumlah padding yang diinginkan. Setelah itu **x** dari ImageView itu saya buat agar sesuai jumlah paddingnya. 

	let outerView = UIView(frame: CGRect(x: 0, y: 0, width: size+padding, height: size) )
	let iconView  = UIImageView(frame: CGRect(x: padding, y: 0, width: size, height: size))
  
***Nah yang ini baru bisa!***

Supaya lebih mudah digunakan, mari kita taro dalam **extension**. 
> Demen banget saya sama fitur extension di Swift ini :-)

	extension UITextField {

	 /// set icon of 20x20 with left padding of 8px 
	 func setLeftIcon(_ icon: UIImage) {

			let padding = 8
			let size = 20

			let outerView = UIView(frame: CGRect(x: 0, y: 0, width: size+padding, height: size) )
			let iconView  = UIImageView(frame: CGRect(x: padding, y: 0, width: size, height: size))
			iconView.image = icon
			outerView.addSubview(iconView)

			leftView = outerView
			leftViewMode = .always  
		}
	}
	

# Cara pake
anggap aja saya punya outlet namanya txOrigin ya, tipenya UITextField

	txOrigin.setLeftIcon(icon_location)
	
# Khasiat
![left view with padding](https://i.stack.imgur.com/3mAqr.png)
		
# RightView?
Mudah. Tinggal diganti aja left nya jadi right.



# Demikian
Lihat di stackoverflow [](http://stackoverflow.com/questions/32525006/how-to-get-left-padding-on-uitextfield-leftview-image/42849074#42849074)

semoga berguna ya. Thanks!

> ***Bye!***

![bye](/images/bye.gif)