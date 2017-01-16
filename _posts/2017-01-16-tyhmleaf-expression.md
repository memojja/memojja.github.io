---
layout: post
title:  "Tyhmeleaf Expression"
date:   2016-07-31 16:16:01 -0600
categories: Java
tags: Java Spring
---






Merhaba arkadaslar bugun bugun Tymleafden bahsedecegim.**Tyhmeleaf** açık kaynak bir Html5 template engine’dir.Servlet tabanlıdır ve Spring’e entegre edilmesi kolaydır bu yüzden spring uygualmaları yazılırken ~~JSP~~ yerine **tyhmeleaf** tercih edilir.4 tip expression vardır diyebiliriz.Bunlar;

**1-Variable Expression ${…} :** Context üzerine bind edilmis degiskenlere erişimde kullanılır.Örnekler;
{% highlight java %}

<span th:text="${name}">Mehmet ARI</span>
<span th:text="${person.name}">Mehmet ARI</span>
<span th:text="${person[0].name}">Mehmet ARI</span>
<span th:text="${person.getName()}">Mehmet ARI</span>

{% endhighlight %}

_Tabi bunların dışında variable expression içerisinde kullanabilecegimiz yardımcı objeler mevcut.Bunlar; lists,calendar,maps,locale,dates gibi objeler._

{% highlight java %}
<span th:text="${#dates.day}"> </span>
{% endhighlight %}

**2-Selection Variable Expression :**
{% highlight java %}


<div th:object="${user}">
   <p>Name: <span th:text=" * {name}">Mehmet</span>.</p>
   <p>Surname: <span th:text="* {surname}">Arı</span>.</p>
   <p>Univercity: <span th:text="* {Univercity}">Karabük Üni</span>.</p>
</div>

{% endhighlight %}

**3-Message Expression #{…} :** Properties dosyasında tanımladığınız değişkenleri basmamızı sağlar.

**4-Link/Url Expression @{…} :** Link ve url tanımlamalarında kullanılır.

{% highlight java %}

<a href="fatura.html" th:href="@{/fatura}">Görüntüle</a>
<a href="fatura.html" th:href="@{/fatura/(faturaId=${f.id})}">Görüntüle</a>
<a href="fatura.html" th:href="@{/fatura/details(faturaId=${o.id}, type='Maximum')}">Görüntüle</a>

{% endhighlight %}

_Gelin ogrendiklerimizle basit bir form örneği yapalım ;_


{% highlight java %}

<form th:action="@{/faturalar}" th:object="${fatura}" th:method="post">
        <table>
            <tr>
                <td>Fatura Type:</td>
                <td><input type="text" th:field="*{type}" /></td>
                <td th:if="${#fields.hasErrors('type')}" th:errors="*{type}">Fatura Type Error will appear here</td>
            </tr>
            <tr>
                <td>Ücret:</td>
                <td><input type="text" th:field="*{amount}" /></td>
                <td th:if="${#fields.hasErrors('amount')}" th:errors="*{amount}">Amount Error will appear here</td>
            </tr>
            <tr>
                <td><button type="submit">Add</button></td>
            </tr>
        </table>
    </form>

{% endhighlight %}

Bu yazimi burada sonlandiriyorum arkadaslar ogrendikce paylasmaya devam edicegim.

Mutlu ve esen kalın :) .
