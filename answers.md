1) ÖRNEK SORU: Öğrenci tablosundaki tüm kayıtları listeleyin.

   CEVAP: select * from ogrenci


2) Öğrenci tablosundaki öğrencinin adını ve soyadını ve sınıfını listeleyin.
    
    SELECT ad,soyad,sinif FROM ogrenci

3) Öğrenci tablosundaki kız öğrencileri listeleyin.

    SELECT * FROM ogrenci WHERE cinsiyet = "k"

4) Öğrenci tablosunda kaydı bulunan sınıfların adını her sınıf bir kez görüntülenecek şekilde listeleyiniz
    
    SELECT distinct sinif FROM ogrenci 
    
5) Öğrenci tablosunda, 10A sınıfında olan kız öğrencileri listeleyiniz.

    SELECT * FROM ogrenci WHERE cinsiyet = "k" AND sinif = "10A"

6) Öğrenci tablosundaki 10A veya 10B sınıfındaki öğrencilerin adını, soyadını ve sınıfını listeleyiniz.

    SELECT ad,soyad,sinif FROM ogrenci WHERE sinif IN ("10A", "10B")

7) Öğrenci tablosundaki öğrencinin adını, soyadını ve numarasını okul numarası olarak listeleyiniz. (as kullanım örneği)

    SELECT ad,soyad,no as "Ogrenci Numarasi" FROM ogrenci

8) Öğrenci tablosundaki öğrencinin adını ve soyadını birleştirip, adsoyad olarak listeleyiniz. (concat, as kullanım örneği)

    SELECT CONCAT(ad," ",soyad) as "AD-SOYAD" FROM ogrenci

9) Öğrenci tablosundaki Adı ‘A’ harfi ile başlayan öğrencileri listeleyiniz.

    SELECT * FROM ogrenci WHERE ad LIKE 'A%'

10) Kitaplar tablosundaki sayfa sayısı 50 ile 200 arasında olan kitapların adını ve sayfa sayısını listeleyiniz.

    SELECT ad,sayfasayisi FROM kitaplar WHERE (sayfasayisi > 50 AND sayfasayisi < 200)

11) Öğrenci tablosunda adı Fidan, İsmail ve Leyla olan öğrencileri listeleyiniz.

    SELECT * FROM ogrenci WHERE ad IN ('fidan', 'ismail', 'leyla')

12) Öğrenci tablosundaki öğrencilerden adı A, D ve K ile başlayan öğrencileri listeleyiniz.

    SELECT * FROM ogrenci WHERE ad LIKE 'A%' OR 'D%' OR 'K%'

13) Öğrenci tablosundaki sınıfı 9A olan Erkekleri veya sınıfı 9B olan kızların adını, soyadını, sınıfını ve cinsiyetini listeleyiniz.

    SELECT ad, soyad, sinif, cinsiyet FROM ogrenci WHERE (sinif = '9A' AND cinsiyet='E') OR (sinif = '9B' AND cinsiyet = 'K')

14) Sınıfı 10A veya 10B olan erkekleri listeleyiniz.

    SELECT * FROM ogrenci WHERE (sinif = '10A' OR sinif = '10B') AND (cinsiyet = 'E')

15) Öğrenci tablosunda doğum yılı 1989 olan öğrencileri listeleyiniz.

    SELECT * FROM ogrenci WHERE dogumyili = 1989

16) Öğrenci numarası 30 ile 50 arasında olan Kız öğrencileri listeleyiniz.

    SELECT * FROM ogrenci WHERE (numara > 30 AND numara < 50) AND (cinsiyet = 'K')

17) Öğrencileri adına göre sıralayınız (alfabetik).

    SELECT * FROM ogrenci ORDER BY ad

18) Öğrencileri adına, adı aynı olanlarıda soyadlarına göre sıralayınız.

    SELECT * FROM ogrenci ORDER BY ad, soyad

19) 10A sınıfındaki öğrencileri okul numarasına göre azalan olarak sıralayınız.

    SELECT * FROM ogrenci WHERE sinif = '10A' ORDER BY no DESC

20) Öğrenciler tablosundaki ilk 10 kaydı listeleyiniz.
    [İPUCU: `Select top tüm mysql versiyonlarında düzgün çalışmaz. LİMİT kullanmak daha faydalıdır`]

    SELECT * FROM ogrenci LIMIT 10

21) Öğrenciler tablosundaki ilk 10 kaydın ad, soyad ve doğum tarihi bilgilerini listeleyiniz.

    SELECT ad, soyad, dogumtarihi FROM ogrenci LIMIT 10

22) Sayfa sayısı en fazla olan kitabı listeleyiniz.

    SELECT * FROM kitap ORDER BY sayfasayisi DESC LIMIT 1

23) Öğrenciler tablosundaki en genç öğrenciyi listeleyiniz.

    SELECT * FROM ogrenci ORDER BY dogumtarihi DESC LIMIT 1    

24) 10A sınıfındaki en yaşlı öğrenciyi listeyin.

    SELECT * FROM ogrenci WHERE sinif = '10A' ORDER BY dogumtarihi ASC LIMIT 1

25) İkinci harfi N olan kitapları listeleyiniz.

    SELECT * FROM kitap WHERE kitapadi LIKE '_N%'

26) Öğrencileri sınıflarına göre gruplayarak listeleyin.

    SELECT sinif, count(*) FROM ogrenci GROUP BY sinif

27) Öğrencileri her sorgulamada sıralaması farklı olacak şekilde rastgele listeleyin.
    [İPUCU: rand() fonksiyonu]

    SELECT 

28) Öğrenci tablosundan Rastgele bir öğrenci seçiniz.

        

29) 10A sınıfından rastgele bir öğrencinin adını, soyadını, numarasını ve sınıfını getirin.


# Esnek
30) Öğrenci tablosunda aynı isimde kaçar öğrenci olduğunu bulmak istiyoruz.
    Öğrenci isimlerinin sayısını "adet" olarak öğrencilerin isimleri "isim" olarak listeleyin.
    [İPUCU: count() ve group by]