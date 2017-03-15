---
title: Back button tanpa 'Back'
layout: post
---

Lagi-lagi  hal yang _tricky_ dalam iOS development. Yaitu terkadang title nya si back button (yang di sebelah kiri di navigation bar) titlenya bukannya 'Back' malah jadi title view controller sebelumnya.

![not back](/images/Back%20Button%20with%20Other%20Title.png){:class="img-responsive"}

Akibatnya, title view controller yang sedang aktif jadi agak menjorok ke kanan. Mungkin ada developer yang yaudahlah  terima apa adanya aja emang begitu. Saya sendiri sebenarnya gak begitu masalahin tampilan hehehe. Tapi kan yaaah pasti ada nanti yang nanya-nanya kenapa yang ini 'Back' yang itu _nggak_ 'Back'. Singkat kata, saya ilangin aja semua 'Back' dari semua Back button. Selesai. Pulang deh. Horee!!  
>Padahal masih siang.

Buat yang mau tau caranya gimana, berikut ini bocorannya:

Klik navigation bar lalu pada tab **attribute inspector** field **title** masukkan space satu aja dan enter.
![how to](/images/removes%20back.png)

Hasilnya...

![no title](/images/Back%20Button%20With%20No%20Title.png)

Demikian!
Semoga berguna!


> ***Bye!***

![Bye-bye](http://i.imgur.com/aSYMQW1.gif)