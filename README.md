Fullstack Projesi React ve Node.js ile
========================================

Bu proje, React frontend ve Node.js/Express backend içeren bir fullstack uygulamasıdır. Bu README, proje yapısını anlamanızı, dosyalar arasında gezinmenizi ve her iki uygulamayı birlikte çalıştırmanızı sağlayacaktır.

📁 Proje Yapısı
Proje dizini, iki ana alt dizine sahiptir: frontend ve backend. Her biri, bağımlılıkları ve komut dosyalarını yöneten kendi package.json dosyasına sahiptir. Ayrıca, her iki uygulamayı tek bir komutla çalıştırmak için kök seviyesinde bir package.json dosyası bulunmaktadır.

Klasör Düzeni
bash
Kopyala
Düzenle
fullstack-app/
│
├── backend/      # Express (Backend) API
├── frontend/     # React (Frontend) Uygulaması
├── package.json  # Ortak bağımlılıklar ve komutlar
└── README.md
Her Bölümün Açıklaması
backend/: Node.js ve Express kullanarak yazılmış tüm sunucu tarafı kodunu içerir, API rotaları, middleware ve backend yapılandırmalarını barındırır.

frontend/: React kullanarak yazılmış tüm istemci tarafı kodunu içerir, bileşenler, stiller ve statik dosyalar burada yer alır.

Root package.json: Ortak bağımlılıkları ve her iki uygulamayı yönetmeye yarayan komut dosyalarını tanımlar.

⚙️ Kurulum
Gereksinimler
Node.js (v14 ve üstü)

npm (v7 ve üstü)

Yükleme
Projeyi kurmak için kök dizinde şu komutu çalıştırarak tüm bağımlılıkları yükleyebilirsiniz:

bash
Kopyala
Düzenle
npm install
Bu komut, frontend ve backend dizinleri için gerekli bağımlılıkları otomatik olarak yükler.

🚀 Projeyi Çalıştırma
Kök package.json dosyasında, frontend ve backend sunucularını aynı anda başlatmanıza yardımcı olacak komutlar bulunmaktadır.

Kullanılabilir Komutlar
Bağımlılıkları Yükle: frontend ve backend dizinlerinde bağımlılıkları yükler.

bash
Kopyala
Düzenle
npm install
Frontend ve Backend'i Başlat: Hem React uygulamasını hem de Node.js sunucusunu aynı anda başlatır.

bash
Kopyala
Düzenle
npm start
React (Frontend) http://localhost:3000 adresinde çalışır.

Express (Backend) http://localhost:5000 adresinde çalışır.

Sadece Backend Başlat:

bash
Kopyala
Düzenle
npm run server
Sadece Frontend Başlat:

bash
Kopyala
Düzenle
npm run client
🔄 Frontend ve Backend Nasıl Çalışır?
React frontend sunucuya HTTP istekleri gönderir ve backend'den gelen verileri görüntüler.

Backend, API olarak hizmet verir ve frontend'den gelen isteklere JSON verisi ile yanıt verir.

Örnek API Rotası: backend/server.js içinde bir örnek rota:

js
Kopyala
Düzenle
app.get('/api/project', (req, res) => {
  res.json({
    studentName: "Smith, John",
    projectName: "Weather App",
    projectUrl: "http://localhost:3000",
    projectDescription: "Gerçek zamanlı hava durumu bilgisi sağlar"
  });
});
CORS (Cross-Origin Resource Sharing): CORS etkinleştirilmiştir, böylece frontend farklı portlarda çalışırken backend API'sine erişebilir (3000 frontend, 5000 backend).

💡 Yapı ile Çalışırken İpuçları
frontend ve backend Arasında Gezinme:

Her iki bölüm için de bağımlılıkları yönetmek için ayrı package.json dosyaları kullanın.

Her bölümdeki bağımlılığı eklemek için npm install <package-name> komutunu kullanın.

API Rotalarını Düzenleme:

backend/server.js dosyasına ihtiyacınıza göre yeni rotalar ekleyebilirsiniz. Daha temiz bir yapı için rotaları ayrı dosyalarda tutup server.js dosyasına import edebilirsiniz.

Frontend-Backend İletişimi:

Frontend'de fetch veya axios gibi kütüphaneleri kullanarak backend API'sine istek gönderin.

Örnek (React bileşeni içinde):

js
Kopyala
Düzenle
useEffect(() => {
  fetch('http://localhost:5000/api/project')
    .then(response => response.json())
    .then(data => setProjectData(data));
}, []);
Ortam Konfigürasyonu:

API URL'leri gibi ayarları her iki bölümde de ortam değişkenleri ile yönetebilirsiniz, özellikle üretim ortamına dağıtım yaparken.

Bu yapı, React frontend ve Node.js backend'inizi bağımsız bir şekilde yönetmenizi sağlar ve her iki kodu tek bir projede düzenli tutmanıza olanak tanır.








