---
title: Membungkam fungsi print nya Swift
layout: post
---

## Waktunya Rilis!!

> dan sepertinya gak perlu lagi melihat log-log yang kita buat dengan fungsi print()

ini kode swift nya:

{% highlight swift %}

func print(items: Any..., separator: String = " ", terminator: String = "\n") {
	
 #if DEBUG

  Swift.print(items, separator: separator, terminator: terminator)
        
 #else
        
  // do nothing
    
 #endif
}
		
{%  endhighlight %}


enjoy!