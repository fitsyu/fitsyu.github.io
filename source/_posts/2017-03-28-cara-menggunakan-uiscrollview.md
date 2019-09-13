---
title: Cara Menggunakan UIScrollView
date: 2017-03-28
tags: swift
thumbnail: "/images/UIScrollView 1.png"
---

UIScrollView kalo kita nggak tau cara pakenya bakalan susah.
Intinya kita harus inget beberapa hal ini tiap kali mau ngedrag UIScrollView ke UIViewController kita.

Inget:

- ScrollView cuma bisa punya satu View di dalemnya sebut aja namanya ContentView
- Patokin leading, trailing, top dan bottom Content View ke ScrollView
- Ukuran untuk View yang di dalem tidak bisa tergantung ke ukuran ScrollView tapi ke selain ScrollView

Setelah mensetup hal-hal di atas barulah kita bisa sepuasnya nambahin apa aja ke dalem ContentView itu. Nanti kalo kontennya lebih besar dari ukuran ScrollView, konten tersebut akan dapat di _scroll_.

# Simak cuplikan berikut!

Jadi ini ceritanya ada satu UIScrollView yang ukurannya sama dengan ukuran root view dalam suatu UIViewController.

## Drag sebuah view ke dalem UIScrollView
Rename view tersebut jadi Content View biar enak nanti pas liat constraint nya

![Step 1](/images/UIScrollView 1.png)

## Patokin leading, trailing, top dan bottom

![Step 1](/images/UIScrollView 2.png)

## Benerin lagi
Bersihkan angka -angka kotor itu

![Step 1](/images/UIScrollView 3.png)

Agar jadi seperti ini

![Step 1](/images/UIScrollView 4.png)

## Tentukan ukuran ContentView
Ukuran content view tidak boleh bergantung ke ScrollView. Pada contoh ini ukuran ContentView _width_ nya sama dengan _width_ super view dan _height_ nya wrap content ke **StackView**

![Step 1](/images/UIScrollView 5.png)

Dapat dilihat yang merah-merah (tkita constraint masih ada yang salah) sudah hilang. Kini UIScrollView dengan ContentView siap digunakan.
# Demikian
Mudah-mudahan berguna. Thanks!

> ***Bye!***

![bye](/images/bye.gif)
