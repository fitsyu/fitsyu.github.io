---
title: Contoh Simpel Memakai Timer di Swift
layout: post
comments: 'true'
---

Ada banyak cara menggunakan Timer pada Swift. 

Contoh simple nya : 


{%  highlight swift %}

Timer.scheduledTimer( withTimeInterval: 1.0, repeats: false,  block: { _ in 
                            
  // kode dalam blok ini akan di _eksekusi_ setelah 1 detik
													
  self.performSegue(withIdentifier: "toVcHome", sender: self)
 }
)

{%  endhighlight %}

Kode di atas berkhasiat untuk membuat transisi boongan (_mock_) dari SplashScreen ke Home menu setelah satu detik.

Demikian!


Selamat menjajal! 

> ***Bye!***

![Bye-bye](http://i.imgur.com/aSYMQW1.gif)

