---
title: UILabel Lebih Dari Satu Baris
layout: post
---

Secara default, UILabel dibuat agar hanya menampilkan satu baris kata saja. 
Namun ada kalanya suatu saat nanti anda akan butuh UILabel yang  menampilkan label yang lebih dari satu baris. 
Contohnya ketika space yang ada lebih sempit dari panjang teks nya. Jadinya kepotong kaya begini:

<img src="{{ site.url }}/assets/cropped-labels.png" width="200" class="center">

Solusi mudahnya mungkin set saja pengaturan fontnya agar mengecil bila tidak ada space.  

<img src="{{ site.url }}/assets/change-font-auto-shrink.png" class="center">

Hasilnya akan tampak seperti di bawah ini:

<img src="{{ site.url }}/assets/auto-shrinked-font.png" width="200" class="center">

Teks tidak terpotong tapi tampilannya jadi tidak konsisten. Ada yang besar ada pula yang kecil. Bila anda masih belum puas, solusinya ada di sini. Terus baca.

Seperti pada umumnya, cara programmer menyelesaikan masalah adalah dengan  mengeksplorasi. Coba perluas sedikit radius blusukan anda. Ada attribute **Lines** di sana. Apa itu?

Gantilah angkanya menjadi **2** lalu jalankan app nya! 

<img src="{{ site.url }}/assets/change-lines-number.png" class="center">


atau di dalam kode 
```swift
@IBOutlet weak var  myLabel: UILabel!

// di dalam suatu fungsi, misal di viewDidLoad()
myLabel.numberOfLines = 2



```

Berikut penampakannya:

<img src="{{ site.url }}/assets/labels-with-two-lines.png" width="300" class="center">

Baiklah sekarang anda tau cara membuat label yang lebih dari satu baris. Hal itu dapat diatasi dengan menyetel property numberOfLines dengan jumlah baris yang diperlukan. Lalu bagaimana bila anda tidak tau berapa tepatnya jumlah baris yang diperlukan ? 

Bila anda tidak tau berapa jumlah baris yang diperlukan, set saja numberOfLines nya menjadi 0. *Lho?*

<img src="{{ site.url }}/assets/change-line-number-to-zero.png" class="center">

Aneh memang rasanya,  anda mungkin berpikir kalo numberOfLinesnya 0 berarti tidak ada label sama sekali. Betul banget. Tapi kalau kita pikirin lebih dalam lagi angka 0 lah angka yang paling tepat untuk mengekpresikan ketidaktauan kita akan sesuatu dan menyerahkannya kepada yang lebih tau. Dengan begini kita gak usah repot menghitung jumlah barisnya dan hasilnya:

<img src="{{ site.url }}/assets/zero-lines-labels.png" width="300" class="center">

Demikian UILabel yang tidak terpotong teksnya dan jumlah barisnya dapat menyesuaikan dengan space yang ada.
Mudah-mudahan bermanfaat.  
Mohon maaf bila ada kesalahan.

Di pos selanjutnya, akan dijelaskan bagaimana membuat superview / parent dari UILabel yang multiline ini menyesuaikan ukurannya dengan ukuran label. Seperti *Wrap Content*  nya Android.

Sampai Jumpa!
