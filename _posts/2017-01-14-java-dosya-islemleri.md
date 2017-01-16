---
layout: post
title:  "Java Dosya Okuma/Yazma İşlemleri"
date:   2015-11-17 16:16:01 -0600
categories: Java
tags: Java
---

Merhaba arkadaslar bugun dosyada okuma/yazma işlemi nasıl yapılır basitce onu göstericeğim.Text olur normal dosya olur network olur hatta database bile olablir okuyacağımız kaynak.
Öncelikle Stream in ne oldugundan bahsedelim.Kaynak ve uygulama arasında bir bağlantı oluşturulur.Bunun üzerinden dosyaya veri yazar yada okuruz.İşte bunu streamler üzerinden yaparız.2 ye ayırabiliriz JAVA da dosya okumayı.(Bunlar birer interfacedir.Javadaki herşey birer interface aslinda)

* **Reader ve Writer Siniflari :** Reader ve Writer Sınıfları ile karakter bazlı işlem yapabiliriz.Gidipte bir resim dosyası okuyamayız.Okuruz ama otomatik texte çevirir yani bir işe yaramaz.İşte onu byte bazlı yapmamız lazım yani Stream Sınıfları ile.Örnegin bir web sitemiz var log tutmamız lazım işte o zaman bu sınıfı kullanabiliriz.

* **Stream Sınıfları :** Stream Sınıfları ile ise byte bazlı işlemleri gerçekleştirebiliriz.Örnegin bir klasör kopyalicaz veya resim kayıt etmemiz lazım bunlar stream sınıfları ile gerçekleştirilir.

##### **Reader ve Writer Siniflari**

Dosya okuma ve yazmada temel mantık sirasiyla;

Önce bir dosya açılır.Sonrasında okuma yapılacaksa okunur,yazma işlemi gerçekleştirilecekse o işlem gerçekleştirilir ve iş bittikten sonra kapatılır.Aslında bukadar basit.

Ozaman uygulama ile bunu pekiştirelim:

{% highlight java %}

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class JavaIO {
	public static void main(String[] args) throws IOException {

		File dosya = new File("/home/memojja/İndirilenler/deneme.txt");
		if (!dosya.exists()) //dosya yok ise ;
			dosya.createNewFile(); //oluştur.

		BufferedWriter yazici = new BufferedWriter(new FileWriter(dosya));
		yazici.write("Mehmet ARI n bu yazdığım alt satırda gözükecek");
		yazici.flush();
		yazici.close();
	}

{% endhighlight %}

{% highlight java %}

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class JavaIO {
	public static void main(String[] args) throws IOException {

		String deger = "";
		File dosya = new File("/home/memojja/İndirilenler/deneme.txt");

		BufferedReader okuyucu = new BufferedReader(new FileReader(dosya));

		while ((deger = okuyucu.readLine()) != null)
			System.out.println(deger);
		        okuyucu.close();
	}
}

{% endhighlight %}

##### **Stream Sınıfları**

Ufak bi resim kopyalama işlemi yapalım.

{% highlight java %}

import java.io.BufferedInputStream;
import java.io.BufferedOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

public class JAVAStreamYazma {
	public static void main(String[] args) throws IOException {
		int a = 0;
		File resim = new File("/home/memojja/Masaüstü/android.png");
		File resim2 = new File("/home/memojja/Masaüstü/android2.png");

		BufferedInputStream okuyucu = new BufferedInputStream(
				new FileInputStream(resim));
		BufferedOutputStream yazici = new BufferedOutputStream(
				new FileOutputStream(resim2));
		while ((a = okuyucu.read()) != -1) {
			byte girdi = (byte) a;
			yazici.write(girdi);
		}

		yazici.flush();
		yazici.close();
		okuyucu.close();
		System.out.println("kopyalandı");
	}

 {% endhighlight %}

 Yazımı burada sonlandırıyorum arkadaslar, sonraki yazilarda bu okuma yazma islemlerini "Socket Programlamada" bir uygulamasini yapacagim.Umarim faydali olmustur.

 Mutlu ve esen kalın. :)
