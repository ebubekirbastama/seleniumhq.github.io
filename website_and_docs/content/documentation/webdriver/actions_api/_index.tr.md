---
title: "Actions API"
linkTitle: "Actions API"
weight: 14
description: >
    Sanal giriş eylemlerini tarayıcıya sağlayan düşük seviye bir arayüz.
---

Yüksek seviyeli [element etkileşimleri]({{< ref "/documentation/webdriver/elements/interactions.md" >}})ne ek olarak, 
[Actions API](https://w3c.github.io/webdriver/#dfn-actions), belirli giriş cihazlarının tam olarak ne yapabileceği konusunda ayrıntılı kontrol sağlar. Selenium, 3 tür giriş kaynağı için bir arayüz sağlar: 
klavye cihazları için tuş girişi, fare, kalem veya dokunma cihazları için işaretçi girişi 
ve kaydırma tekerlek cihazları için kaydırma girişleri (Selenium 4.2'de tanıtıldı). 
Selenium, belirli girdi ve performans yöntemini çağırmak ve bunları zincirlemek ve hepsini bir seferde çalıştırmak için ilişkilendirilmiş yürütme yöntemini çağırmak için tek tek eylem komutları oluşturmanıza izin verir.

## Eylem Oluşturucu

Eski JSON Wire Protocol'den yeni W3C WebDriver Protocol'e geçişte,
eylemlerin düşük seviyeli yapı taşları özellikle detaylandı. Bu son derece
güçlüdür, ancak her giriş cihazının kullanımı için birden fazla yol vardır ve birden fazla cihazı yönetmeniz gerekiyorsa, bunlar arasında uygun senkronizasyonu sağlamak sizin sorumluluğunuzdadır.

Neyse ki, muhtemelen düşük seviye komutları doğrudan nasıl kullanacağınızı öğrenmeniz gerekmez, çünkü
yapmak isteyebileceğiniz hemen hemen her şey, sizin için düşük seviye komutları birleştiren bir kolaylık yöntemi ile sağlanmıştır. Bunlar, 
[keyboard]({{< ref "keyboard" >}}), [mouse]({{< ref "mouse" >}}), [pen]({{< ref "pen" >}}) ve [wheel]({{< ref "wheel" >}}) sayfalarında belgelenmiştir.

## Bekletme

İşaretçi hareketleri ve tekerlek kaydırma işlemi, eylem için bir süre belirlemek için kullanıcıya izin verir, ancak bazen işlerin düzgün çalışması için eylemler arasında bir bekleme süresine ihtiyacınız olabilir.

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="examples/java/src/test/java/dev/selenium/actions_api/ActionsTest.java#L21-L28" >}}
{{< /tab >}}
{{< tab header="Python" >}}
{{< gh-codeblock path="examples/python/tests/actions_api/test_actions.py#L13-L20" >}}
{{< /tab >}}
{{< tab header="CSharp" >}}
{{< badge-version version="4.2" >}}
{{< gh-codeblock path="examples/dotnet/SeleniumDocs/ActionsAPI/ActionsTest.cs#L18-L25" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< badge-version version="4.2" >}}
{{< gh-codeblock path="examples/ruby/spec/actions_api/actions_spec.rb#L12-L19" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< gh-codeblock path="examples/javascript/test/actionsApi/actionsTest.spec.js#L20-L27" >}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< gh-codeblock path="examples/kotlin/src/test/kotlin/dev/selenium/actions_api/ActionsTest.kt#L22-L29" >}}
{{< /tab >}}
{{< /tabpane >}}

## Tüm Eylemleri Serbest Bırakma

Unutulmaması gereken önemli bir şey, sürücünün oturum boyunca tüm giriş öğelerinin durumunu hatırlamasıdır. Bir eylem sınıfının yeni bir örneğini oluştursanız bile, bastırılmış tuşlar ve 
işaretçi düğmelerinin konumu, daha önce gerçekleştirilmiş bir eylemin bıraktığı durumda olacaktır.

Tüm mevcut bastırılmış tuşları ve işaretçi düğmelerini serbest bırakmak için özel bir yöntem vardır.
Bu yöntem, her bir dilden farklı şekillerde uygulanır çünkü
perform yöntemiyle yürütülmez.

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="examples/java/src/test/java/dev/selenium/actions_api/ActionsTest.java#L46" >}}
{{< /tab >}}
{{< tab header="Python" >}}
{{< gh-codeblock path="examples/python/tests/actions_api/test_actions.py#L37" >}}
{{< /tab >}}
{{< tab header="CSharp" >}}
{{< gh-codeblock path="examples/dotnet/SeleniumDocs/ActionsAPI/ActionsTest.cs#L44" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< gh-codeblock path="examples/ruby/spec/actions_api/actions_spec.rb#L36" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< gh-codeblock path="examples/javascript/test/actionsApi/actionsTest.spec.js#L44" >}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< gh-codeblock path="examples/kotlin/src/test/kotlin/dev/selenium/actions_api/ActionsTest.kt#L47" >}}
{{< /tab >}}
{{< /tabpane >}}
