
## SmartLibrary – Kütüphane Yönetim Sistemi

Ders: Nesneye Dayalı Programlama II

Hazırlayan: Beyza Çevik

Öğrenci No: 20230108010

Not: Proje kodları main branch üzerinde değil, master branch altında bulunmaktadır.

## 1. Projenin Amacı

SmartLibrary, Java ve SQLite kullanılarak geliştirilen temel bir kütüphane yönetim sistemidir.
Projenin amacı; nesneye dayalı programlama prensiplerini uygulayarak kitap, öğrenci ve ödünç işlemlerinin yönetilebildiği konsol tabanlı bir sistem oluşturmaktır.

Uygulama ile:

Yeni kitap ve öğrenci eklenebilir,

Mevcut kayıtlar listelenebilir,

Ödünç verme ve teslim alma işlemleri yapılabilir,

Ödünç listesi ilişkisel olarak görüntülenebilir.

## 2. Kullanılan Teknolojiler

Java (OOP yapısıyla)

SQLite

JDBC + PreparedStatement

ArrayList Koleksiyon Yapıları

IntelliJ IDEA

SQLite JDBC Driver

Harici framework kullanılmamıştır, tüm işlem JDBC üzerinden yürütülmektedir.

## 3. Sınıf Yapısı
1. BaseEntity

Tüm varlıkların ortak id alanını içeren temel sınıftır.

2. Book

id

title

author

year

3. Student

id

name

department

## 4. Loan

id

bookId

studentId

dateBorrowed

dateReturned

## 5. Database

SQLite bağlantısını kurar

Tabloları oluşturur

Bağlantının doğruluğunu kontrol eder

## 4. Repository Yapısı

Her tablo için ayrı bir repository sınıfı bulunur:

BookRepository

StudentRepository

LoanRepository

Repository’lerde ortak CRUD metotları yer alır:

add()

update()

delete()

getById()

getAll()

LoanRepository, ek olarak kitapların ödünçte olup olmadığını kontrol eden ek fonksiyonlar içerir.

## 5. Veritabanı Yapısı
books

| id | title | author | year |

students

| id | name | department |

loans

| id | bookId | studentId | dateBorrowed | dateReturned |

Uygulama ilk kez çalıştırıldığında tablolar otomatik oluşturulur.

## 6. Uygulama Menüsü

Konsol menüsünde kullanıcıya şu işlemler sunulur:

Kitap ekle

Kitapları listele

Öğrenci ekle

Öğrencileri listele

Kitap ödünç ver

Ödünç kayıtlarını görüntüle

Kitap geri teslim al

Çıkış

Ödünç listeleme ekranında kitap adı ve öğrenci adı ilişkisel olarak gösterilir.

## 7. Kurulum Adımları

Projeyi indirin veya clonelayın.

sqlite-jdbc sürücüsünü lib klasörüne ekleyin.

IntelliJ IDEA → Project Structure → Dependencies kısmından JAR dosyasını projeye tanıtın.

Main.java dosyasını çalıştırın.

Veritabanı (smartlibrary.db) otomatik oluşturulur.

## 8. Sonuç

SmartLibrary, Nesneye Dayalı Programlama II dersinin gereksinimlerini karşılayan tam işlevsel bir uygulamadır.
OOP yapıları, repository katmanları, JDBC kullanımı ve veritabanı ilişkileri temiz ve anlaşılır bir şekilde uygulanmıştır.

Proje; kitap, öğrenci ve ödünç yönetiminin temel prensiplerini göstermek amacıyla hazırlanmış olup geliştirilmeye müsaittir.
