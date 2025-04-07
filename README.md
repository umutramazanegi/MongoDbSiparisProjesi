# MongoDB Sipariş Projesi 🇹🇷

Bu proje, C# (.NET Framework) ile geliştirilmiş, MongoDB veritabanında saklanan siparişleri yönetmek için temel CRUD (Oluşturma, Okuma, Güncelleme, Silme) işlemlerini gösteren basit bir Windows Forms uygulamasıdır.

## 🌟 Özellikler

*   MongoDB'deki tüm siparişleri listeleme.
*   Yeni bir sipariş oluşturma ve MongoDB'ye kaydetme.
*   Mevcut bir siparişi ID'sini kullanarak MongoDB'de güncelleme.
*   ID'sini kullanarak MongoDB'den bir sipariş silme.
*   ID ile belirli bir siparişi getirme ve görüntüleme.
*   Etkileşim için basit bir Windows Forms arayüzü.

---

## 🛠️ Kullanılan Teknolojiler

*   C# (.NET Framework 4.7.2)
*   Windows Forms (WinForms)
*   MongoDB
*   MongoDB C# Driver
*   Visual Studio 2019/2022

---

## 📋 Ön Gereksinimler

Projeyi çalıştırmadan önce sisteminizde şunların kurulu olması gerekir:

1.  **Visual Studio:** 2019 veya 2022 sürümü (.NET Desktop Development iş yükü ile).
2.  **.NET Framework 4.7.2:** (Genellikle Visual Studio ile birlikte gelir).
3.  **MongoDB Server:** Yerel makinenizde veya erişilebilir bir sunucuda çalışan bir MongoDB örneği.

---

## 몽고DB 📦 MongoDB Kurulumu ve Ayarları

Bu proje veri depolamak için MongoDB kullanır. MongoDB'nin kurulu ve çalışır durumda olması gerekmektedir.

**1. MongoDB Community Server İndirme:**
   *   MongoDB'nin resmi web sitesine gidin: [https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)
   *   İşletim sisteminize uygun (genellikle Windows x64 MSI) sürümü indirin.

**2. MongoDB Kurulumu (Windows):**
   *   İndirilen MSI dosyasını çalıştırın.
   *   Kurulum sihirbazını takip edin. Genellikle "Complete" (Tam) kurulum seçeneği uygundur.
   *   **"Install MongoDB as a Service"** seçeneğini işaretli bırakın. Bu, MongoDB'nin arka planda bir Windows hizmeti olarak çalışmasını sağlar.
        *   Servis Adı (Service Name): `MongoDB` (varsayılan)
        *   Veri Dizini (Data Directory): `C:\Program Files\MongoDB\Server\[versiyon]\data\` (varsayılan)
        *   Log Dizini (Log Directory): `C:\Program Files\MongoDB\Server\[versiyon]\log\` (varsayılan)
   *   **"Install MongoDB Compass"** seçeneğini işaretleyebilirsiniz. Compass, MongoDB için kullanışlı bir grafik arayüz (GUI) aracıdır.
   *   Kurulumu tamamlayın.

**3. MongoDB Servisini Kontrol Etme:**
   *   Windows Hizmetleri'ni açın (Çalıştır'a `services.msc` yazın).
   *   Listede "MongoDB Server (MongoDB)" adlı hizmeti bulun.
   *   Durumunun "Çalışıyor" (Running) olduğundan emin olun. Değilse, sağ tıklayıp "Başlat" (Start) seçeneğini seçin.

**4. (Opsiyonel) MongoDB Compass ile Bağlanma:**
   *   Eğer kurduysanız, MongoDB Compass'ı başlatın.
   *   Varsayılan bağlantı adresi genellikle `mongodb://localhost:27017` şeklindedir. Bu adresle bağlanın.
   *   Uygulama çalıştığında otomatik olarak `SiparisDB` adında bir veritabanı ve içinde `Orders` adında bir koleksiyon (tablo) oluşturacaktır. Compass ile bu veritabanını ve koleksiyonu görebilirsiniz.

---

## 🚀 Proje Kurulumu ve Çalıştırma

1.  Bu repoyu klonlayın: `git clone https://github.com/kullanici-adiniz/MongoDbSiparisProjesi.git` (kendi kullanıcı adınızla değiştirin)
2.  Visual Studio ile `MongoDbSiparisProjesi.sln` dosyasını açın.
3.  **Bağlantı Dizesini Kontrol Edin/Güncelleyin:**
    *   `MongoDbSiparisProjesi/Services/OrderOperation.cs` dosyasını açın.
    *   MongoDB bağlantı dizesinin (connection string) doğru olduğundan emin olun. Varsayılan olarak `mongodb://localhost:27017` kullanılır. Eğer MongoDB farklı bir adreste veya portta çalışıyorsa ya da kimlik doğrulama gerektiriyorsa, bu dizeyi güncellemeniz gerekir.
    *   *Not: Proje şu anda veritabanı adını (`SiparisDB`) ve koleksiyon adını (`Orders`) kod içinde tanımlamaktadır.*
4.  Projeyi derleyin (Build Solution) (Ctrl+Shift+B).
5.  Projeyi çalıştırın (Start) (F5).

---

## 💻 Kullanım

1.  Uygulamayı çalıştırın.
2.  Sipariş detaylarını girmek için metin kutularını (Müşteri Adı, İlçe, Şehir, Toplam Fiyat) kullanın.
3.  Yeni bir sipariş oluşturmak için "Ekle" butonuna tıklayın.
4.  Tüm siparişleri grid üzerinde görüntülemek için "Listele" butonuna tıklayın.
5.  **Güncelleme/Silme/ID ile Getirme için:**
    *   Grid üzerinde veya bilinen bir `OrderId` değerini "Sipariş Id" metin kutusuna girin (MongoDB ObjectId formatında olmalıdır).
    *   **Güncelleme:** Diğer metin kutularını yeni değerlerle doldurun ve "Güncelle" butonuna tıklayın.
    *   **Silme:** "Sil" butonuna tıklayın.
    *   **ID ile Getirme:** "Getir" butonuna tıklayın.
6.  DataGridView (ızgara) kontrolü, Listeleme veya ID ile Getirme işlemlerinin sonuçlarını gösterecektir.
