---
title: Membuat Subtitle Pada Navigation Item
date: 2017-03-17
tags: swift
---

Navigation Item hanya support title saja. Tapi tahukan kita ada property bernama **titleView** yang membolehkan title tersebut dapat diganti dengan view apa saja. (asal muat).

![](/images/title doang.png)


> Setelah pulang dari sini kita akan punya navigation item yang ada subtitlenya.


Ikuti langkah-langkah mudah berikut:

# Download zip
Ada 3 file dalam zip ini.  [Download dulu ](/files/SubtitleView.zip)
[](http://)
# SubtitleView
![](/images/subtitle view xib.png)

Tambahkan file SubtitleView.xib ini ke project Xcode.
kita bisa menggunakan File -> Add Files to ...


# Kode untuk SubtitleView

Tambahkan juga file SubtitleView.swift ke project Xcode kita.
Atau buat file Swift baru yang isinya sebagai berikut:

``` swift
//
//  SubtitleView.swift
//  Subtitle View
//
//  Created by Fitsyu on 3/17/17.
//  Copyright © 2017 fitsyu. All rights reserved.
//

import UIKit

final class SubtitleView: UIView {

    // MARK: Outlets
    @IBOutlet weak var txTitle: UILabel!
    @IBOutlet weak var txSubTitle: UILabel!

}

```

lalu buka SubtitleView.xib dan ganti kelasnya jadi SubtitleView.

# Loading SubtitleView
Kode dalam file 'Useful Extension.swift' ini berguna untuk me _load_ SubtitleView
dan wrappernya.

Jadi jangan sampai lupa untuk ditambahkan juga ke dalam project.
# Coba
        navigationItem.title = "Cuma Title"
        navigationItem.setSubtitle("Sekarang ada subtitlenya 😄")

Letakkan misalnya di _viewDidLoad()_
# Hasil
Kalau berhasil akan seperti ini

![](/images/with subtitle.png)


# Demikian

Semoga berguna!


> ***Bye!***

![Bye-bye](http://i.imgur.com/aSYMQW1.gif)
