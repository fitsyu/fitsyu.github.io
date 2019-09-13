---
title: Mengatasi Keyboard Yang Menutupi UITextField
date: 2017-04-10
tags: swift
---

# Revelation
Tidak seperti Android,  keyboard (soft) di iOS akan menutupi apapun yang ada di bawahnya dan tidak ada penganganan otomatis dari sistem operasi.

Suatu bonus extra dari Apple agar kita semakin rajin menulis kode. Tapi ini adalah masalah yang umum dan dapat dipastikan siapapun pasti merasakan kagetnya pas keyboard muncul,  UITextField atau apapun di bawah keyboard jadi tidak kelihatan.

# Reconciliation

Untungnya ada cara untuk mengetahui kapan keyboard muncul dan kapan keyboard kembali tersembunyi. Dengan cara ini seorang developer dapat mengatur ulang posisi UITextField atau sekalian ViewController agar menjadi agak naik dan turun kembali setelah keyboardnya selesai digunakan.



## Untuk itu dapatkanlah ***free code***  di bawah ini :

[Magic Extension](https://github.com/fitsyu/Handling-Overlaying-iOS-Keyboard/blob/master/Handling%20Overlaying%20Keyboard/Extension.swift)


## Dan inilah cara menggunakannya:

``` swift
override func viewDidLoad() {
        super.viewDidLoad()

        TheKeyboardProblemEndsHere

 }

```

Bila textfield berada di dalam UIScrollView:

``` swift
@IBOutlet weak var scrollView: UIScrollView!

override func viewDidLoad() {
        super.viewDidLoad()

        scrollView.TheKeyboardProblemEndsHere

}
```

Mudahkan?
> Silahkan mencoba!

# Bukti
Silahkan lihat video ini [Demo](https://github.com/fitsyu/Handling-Overlaying-iOS-Keyboard/blob/master/Demo/Demo.m4v)
# Demikian
Mudah-mudahan berguna. Thanks!

> ***Bye!***

![bye](/images/bye.gif)
