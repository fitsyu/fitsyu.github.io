---
title: Membuat Next Button Keyboard Bekerja
date: 2017-05-01
tags: swift
---

Tombol ___next___ pada soft keyboard dapat dibuat dengan men _set_ return button style menjadi ___next___. Namun itu hanya merubah tampilan saja yang tidak berguna bila tidak diatur.

Dengan membuat objek yang perannya sebagai UITextFieldDelegate, kita dapat mengetahui kapan tombol tersebut ditekan. Yaitu lewat fungsi ___shouldReturn( textField: UITextField ) -> Bool___ . Nah dari sinilah kita bisa membuka textfield berikutnya yang harus diedit ketika tombol ___next___ ditekan.

Ada banyak cara untuk mengerjakannya dan secara umum dapat dibagi menjadi dua:
1. Static
2. Dynamic

## Cara Static
Di sini kita tentukan textfield yang akan dibuka (_becomeFirstResponder_) berdasarkan textField yang sedang aktif.

Misalkan ada  UITextField dua biji: txNama dan txLevelKejujuran

Bila yang aktif (yang sedang diedit) saat ini adalah txNama maka tutup  txNama dengan  resignFirstResponder dan buka  txLevelKejujuran dengan becomeFirstResponder.
Selain itu maka tutup saja apapun yang sedang aktif.


Untuk jumlah textfield yang sedikit ( < 4 ) dan sekitarnya, tentu masih mudah untuk diterapkan. Tapi bagaimana bila seluruh View berisi lebih dari 10 UITextField. Waaaw.

## Cara Dinamic
Cara ini memang akan lebih merepotkan namun percayalah tiada yang sia-sia. Hasil dari repot itu ialah kita tidak perlu lagi menentukan secara _manual_ textfield mana dibuka setelah textfield yang mana.

Pertama yang dibutuhkan adalah dua buah property pada objek yang berperan sebagai UITextFieldDelegate yang kemungkinan besar adalah ViewController yang terpasang outlet UITextField di dalamnya.
Dua property tersebut adalah:
List dari UITextField dan activeTextField

``` swift
var  textFields: [ UITextField ] = []
activeTextField: UITextField?
```

Lalu silahkan _textFIelds_ diinisialisasi dengan mengisikan outlet-outlet text field sesuai urutannya. Untuk activeTextField tidak perlu diinisalisasi karena tipenya yang optional yang default nil.
