---
title: System dwójkowy
date: '2016-02-11 21:58:47 +0100'
categories:
- Programowanie
- Wiedza ogólna
permalink: /system-dwojkowy/
header:
    teaser: /assets/images/2016/02/11_system_dwojkowy_artykul.png
    overlay_image: /assets/images/2016/02/11_system_dwojkowy_artykul.png
    caption: "[&copy; koniu_87](https://www.flickr.com/photos/koniu_87/)"
excerpt: Nawet nie wiecie jak się cieszę :) W życiu nie powiedziałbym, że w tak krótkim czasie uda się zebrać 10000000 polubień na Facebooku! Świętujemy z fanfarami :) Z okazji okrągłej liczby króciutki artykuł o innej notacji zapisywania liczb. Dzisiaj dowiemy się czym jest system dwójkowy. Po przeczytaniu artykułu zrozumiecie dlaczego 1024 to okrągła liczba dla programistów ;)
disqus_page_identifier: 118 http://www.samouczekprogramisty.pl/?p=118
---

## Czym różni się cyfra od liczby?

Cyfra i liczba to dwie różne rzeczy. Cyfra to reprezentacja graficzna liczby np. znak 9. Cyfra to znak graficzny podobnie jak litera. Liczba to wartość, która może składać się z wielu cyfr. Wyjaśniłem tę różnicę na początku ponieważ przyda się ona do zrozumienia pozostałej części artykułu.

## Suma i iloczyn

Każdy z nas miał to na matematyce, jednak dla przypomnienia wyjaśnię jeszcze i te pojęcia. 1 + 2 = 3. To jest operacja dodawania. Wynikiem operacji dodawania jest suma.
2 \* 3 = 6. To jest operacja mnożenia. Wynikiem operacji mnożenia jest iloczyn.

Pojęcia te można ze sobą łączyć opisując dłuższe równania.
1 \* 2 + 3 \* 4 = 14 można opisać jako sumę iloczynów,
(1 + 2) \* (3 + 4) = 21 można opisać jako iloczyn sum.

## System dziesiętny

1234, ot zwykła liczba. Liczba zapisana przy pomocy czterech cyfr. Takiej notacji uczyliśmy się od początku naszego życia. W ten sposób liczymy pieniądze, upływające lata czy mierzymy nasz wzrost. A co myślisz o liczbie 10011010010 ;) ? Okazuje się że 10011010010 zapisane binarnie to ta sama liczba co 1234 zapisana w systemie dziesiętnym.

Zanim przejdziemy do systemu binarnego omówmy trochę dokładniej system dziesiętny. Będzie tu trochę matematyki, jednak to nic trudnego i zupełnie nie ma się czego bać :).

{% include newsletter-srodek.md %}

## Potęgi

- 10<sup>0</sup> = 1 (10 do potęgi 0 równa się 1) właściwie to każda liczba większa od zera podniesiona do „zerowej potęgi” równa się 1.
- 10<sup>1</sup> = 10
- 10<sup>2</sup> = 100
- 10<sup>3</sup> = 1000
i tak dalej...

Teraz zapiszmy trochę inaczej naszą liczbę z przykładu:
<div class="highlight">
<pre class="highlight">
<code>
1 * 1000 + 2 * 100 + 3 * 10 + 4 * 1 =
1 * 10<sup>3</sup> + 2 * 10<sup>2</sup> + 3 * 10<sup>1</sup> + 4 * 10<sup>0</sup> = 1234
</code>
</pre>
</div>

Innymi słowy każdą liczbę w systemie dziesiętnym możemy zapisać przy pomocy sumy iloczynów potęg liczby 10. Może się to wydawać trochę skomplikowane jednak to nic trudnego, po prostu słownie opisałem 1 \* 10<sup>3</sup> + 2 \* 10<sup>2</sup> + 3 \* 10<sup>1</sup> + 4 \* 10<sup>0</sup>.

Jeśli 10 nazwiemy bazą systemu dziesiętnego to cyfry, które służą do zapisywania liczb w tym systemie są z zakresu 0 do 9. Zapamiętaj, że tę własność można uogólnić. Innymi słowy jeśli bazę systemu zapisu liczb zastąpimy X wówczas możemy powiedzieć, że liczbę w tym systemie można zapisać przy pomocy cyfr od 0 do X-1[^umowa].

[^umowa]: Oczywiście to jest umowne, równie dobrze można używać innych symboli. Np w systemie szesnastkowym stosujemy cyfry 0-9 oraz litery a-f.

A co stałoby się gdybyśmy potęgi 10 zamienili potęgami 2? Powstałby system binarny zapisywania liczb :).

## System binarny, system dwójkowy

System binarny jest bardzo podobny do systemu dziesiętnego:
- podobnie jak podstawą w systemie dziesiętnym, system binarny ma swoją podstawę. W systemie dziesiętnym jest to 10. W systemie binarnym podstawą jest 2,
- podobnie jak w systemie dziesiętnym cyframi, które można używać do zapisu liczb są cyfry z zakresu 0 do (podstawa – 1). Więc w systemie dziesiętnym mamy zakres od 0 do 9. W systemie binarnym są to tylko dwie cyfry 0 lub 1,
- podobnie jak w systemie dziesiętnym każdą liczbę można wyrazić za pomocą dodawania kolejnych potęg pomnożonych przez liczbę (10<sup>3</sup> \* 1 + 10<sup>2</sup> \* 2 + …), podobnie jest w systemie dwójkowym.

### Potęgi 2

- 2<sup>0</sup> = 1
- 2<sup>1</sup> = 2
- 2<sup>2</sup> = 4
- 2<sup>3</sup> = 8
- 2<sup>4</sup> = 16
- 2<sup>5</sup> = 32
- 2<sup>6</sup> = 64
- 2<sup>7</sup> = 128
- 2<sup>8</sup> = 256
- 2<sup>9</sup> = 512
- 2<sup>10</sup> = 1024

Więc spróbujmy teraz zapisać naszą przykładową liczbę 1234 w systemie binarnym

<div class="highlight">
<pre class="highlight">
<code>
1024 + 128 + 64 + 16 + 2 =
1 * 2<sup>10</sup> + 1 * 2<sup>7</sup> + 1 * 2<sup>6</sup> + 1 * 2<sup>4</sup> + 1 * 2<sup>1</sup> =
1 * 2<sup>10</sup> + 0 * 2<sup>9</sup> + 0 * 2<sup>8</sup> + 1 * 2<sup>7</sup> + 1 * 2<sup>6</sup> + 0 * 2<sup>5</sup> +
1 * 2<sup>4</sup> + 0 * 2<sup>3</sup> + 0 * 2<sup>2</sup> + 1 * 2<sup>1</sup> + 0 * 2<sup>0</sup>
</code>
</pre>
</div>

Mając już zapis liczby jako sumę iloczynów kolejnych potęg możemy spisać kolejne mnożne: 1, 0, 0, 1, 1, 0, 1, 0, 0, 1 i 0. Łącząc je w całość powstaje nam 10011010010 czyli nic innego jak 1234 zapisane w systemie binarnym.

## Przekształcanie liczby do postaci binarnej

Wiesz już czym jest postać binarna. Nadszedł czas na algorytm, który pozwoli Ci przekształcić liczbę dziesiętną w binarną. Zanim do niego przejdziemy musisz wiedzieć czym jest dzielenie całkowitoliczbowe. Wynikiem całkowitoliczbowego dzielenia 5 / 2  jest 2, resztą z tego dzielenia jest 1. Wynikiem całkowitoliczbowego dzielenia 4 / 2 jest 2, reszta z tego dzielenia wynosi 0.

Algorytm przekształcenia liczby w postaci dziesiętnej na binarną:

1. Podziel liczbę całkowitoliczbowo przez 2. Zapisz resztę z dzielenia jako pierwszą cyfrę w postaci binarnej. Przypisz do liczby wynik z dzielenia,
2. Jeśli wynik dzielenia jest większy od zera przejdź do pierwszego kroku.

Poniżej przekształcenie liczby 21 na postać binarną:

1. Liczba to 21. 21 / 2 = 10 reszty 1, aktualna postać binarna `1`,
2. 10 > 0, idziemy dalej,
3. Liczba to 10. 10 / 2 = 5 reszty 0, aktualna postać binarna `01`,
4. 5 > 0, idziemy dalej,
5. Liczba to 5. 5 / 2 = 2 reszty 1, aktualna postać binarna `101`,
6. 2 > 0, idziemy dalej,
7. Liczba to 2. 2 / 2 = 1 reszty 0, aktualna postać binarna `0101`,
8. 1 > 0, idziemy dalej,
9. Liczba to 1. 1 / 2 = 0 reszty 1, aktualna postać binarna `10101`,
10. 0 > 0 nie jest spełnione. Koniec algorytmu. Postać binarna liczby 21 to `10101`

Spróbuj napisać program, który realizuje ten algorytm. Możesz sprawdzić poprawność wyniku używając metody [`Integer.toBinaryString`](https://docs.oracle.com/javase/9/docs/api/java/lang/Integer.html#toBinaryString-int-). Polecam napisanie kilku [testów jednostkowych]({% post_url 2016-10-29-testy-jednostkowe-z-junit %}), które sprawdzą poprawność Twojego rozwiązania.

## Dodatkowe materiały do nauki

> W komentarzu InfW4 wspomniał o ciekawych źródłach, dzięki za wskazówkę ;)

Podobnie jak komentujący miałem przyjemność uczęszczać na kursy prof. Janusza Biernata na Politechnice Wrocławskiej, chociaż artykuł nie powstał w oparciu o materiały z Jego książek jeśli interesuje Cię ta tematyka i chciałbyś spojrzeć na temat z bardziej teoretycznej strony możesz zajrzeć do książki, którą pamiętam ze studiów (ostrzegam, jest mocno teoretyczna): _Metody i układy arytmetyki komputerowej - Janusz Biernat._

## Podsumowanie

Teraz, wiedząc już jak działa system binarny wiesz już skąd wzięła się ta ogromna liczba polubień. 10000000 w systemie binarnym to 2<sup>7</sup> \* 1 czyli 128 :) Jak zwykle mam dla Ciebie ćwiczenia na koniec. Spróbuj zapisać liczby 321 i 2048 w systemie binarnym.

Jeśli chcesz wyższego poziomu trudności zapisz liczby 1024 i 321 w systemie ósemkowym (w systemie, którego podstawą jest 8).

I jak? Trudne? Jeśli masz pytania zadaj je w komentarzach, postaram się pomóc. Bardzo dziękuję Ci za przeczytanie artykułu, jeśli chcesz wiedzieć o najnowszych wpisach polub stronę na Facebooku.

Na koniec mam do Ciebie jeszcze jedną prośbę. Zależy mi na tym, żeby dotrzeć do jak największej liczby czytelników więc jeśli mógłbyś polecić blog swoim znajomym byłbym wdzięczny. Z góry dziękuję i do następnego razu!

PS. Autorem zdjęcia z tytułem artykułu jest mój kolega Wojtek, inne zdjęcia jego autorstwa możecie zobaczyć na [https://www.flickr.com/photos/koniu\_87/](https://www.flickr.com/photos/koniu_87/).
