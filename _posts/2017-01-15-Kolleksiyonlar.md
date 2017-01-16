---
layout: post
title:  "Java Kolleksiyonlar"
date:   2015-11-17 16:16:01 -0600
categories: Java
tags: Java
---


Merhaba arkadaslar bugun kisaca javada kolleksiyonlari anlaticagim.
Koleksiyonlar bir grup değişkeni aynı değişken içerisinde gruplamaya,kümelemeye yarar.Kisaca Java daki veri yapılarınin implemantasyonu.Aşağıdaki gorselde hiyerarsini inceleyebilirsiniz.

![](../../images/collection.jpg)

* **Set :** Küme mantığı ile çalışır.Matematikdeki kümeler ile aynı.Belirli bir sıra ile kayıt edilmez rastgele kayıt edilir.Aynı elemandan birden fazla olamaz.
* **List :** Koyulduğu sıra ile kayıt edilir.Aynı eleman birden fazla koyulabilir.
* **Map :** Veriler key-value cifti ile kayit edilir.

Tabi bunlar çok genel açıklamalar.Örneklerde de sadece kullanımını göstericegim çok farklı methodları var arama,sıralama,silme,…İhtiyacınız oldu zaman eger eclipse kullaniyorsaniz ctrl space yaparak ilgili methodlari gorebilirsiniz.

##### **ArrayList örneği.**


{% highlight java %}

import java.util.ArrayList;
import java.util.List;

public class Collection {
	public static void main(String[] args) {

		List mylist = new ArrayList(); // ArrayListin özelliklerini almaz.Polimorfik tanımlama.											
		mylist.add(5);
		mylist.add(77);
		mylist.add(99);
		mylist.remove(0);

		for (Integer integer : mylist)
			System.out.println(integer);


	}
}
// Ekran Çıktısı
// 77
// 99

{% endhighlight %}

##### **HashSet örneği.**


{% highlight java %}


import java.util.HashSet;

public class Collection2 {
	public static void main(String[] args) {

		HashSet mySet = new HashSet();

		mySet.add("Kaan");
		mySet.add("Eda");
		mySet.add("Talha");
		mySet.add("Kubra");

		for (String string : mySet)
			System.out.println(string);


	}

}
//Ekran çıktısı
//Talha
//Kubra
//Eda
//Kaan

{% endhighlight %}

##### **HashMap örneği.**

_Maplari foreach ile direk yazdıramayız.keySet() methodu ile sete çevirip öyle yazdırabiliriz._

{% highlight java %}

import java.util.HashMap;
import java.util.Set;

public class Collection3 {
	public static void main(String[] args) {
		HashMap<Integer, String> myMap = new HashMap<Integer, String>();
		myMap.put(6, "Ankara");
		myMap.put(78, "Karabük");
		myMap.put(34, "İstanbul");
		myMap.put(42, "Konya");
		myMap.remove(78);

		Set anahtar = myMap.keySet();

		for (Integer integer : anahtar)
			System.out.println(myMap.get(integer));


	}
}

{% endhighlight %}
