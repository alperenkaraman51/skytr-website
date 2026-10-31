# Uzm. Psk. Tuba Güngör Aslan Web Sitesi
**Hedef URL:** `skytryazilim.com/tubagungoraslan`

Google Stitch tasarımından derlenen ve üretime hazır (production-ready) hale getirilen statik web sitesidir.

---

## 📁 Proje Klasör Yapısı

```
tubagungoraslan/
├── index.html                   # Ana Sayfa
├── hakkimda.html                # Özgeçmiş & Klinik Yolculuk
├── calisma-alanlari.html        # Hizmetler & Terapi Alanları
├── iletisim.html                # İletişim, Randevu & Harita
├── .htaccess                    # Apache/cPanel temiz URL yönlendirmeleri
├── calisma-alanlari/
│   └── index.html               # Clean URL desteği (/tubagungoraslan/calisma-alanlari)
├── hakkimda/
│   └── index.html               # Clean URL desteği (/tubagungoraslan/hakkimda)
├── iletisim/
│   └── index.html               # Clean URL desteği (/tubagungoraslan/iletisim)
└── README.md                    # Bu dokümantasyon
```

> **Not:** Ayrıca tüm bu içeriğin tek tıkla yüklenebilir arşiv hali `tubagungoraslan.zip` olarak oluşturulmuştur.

---

## 🚀 Yayına Alma (Deploy) Rehberi

Web sitenizin altyapısına göre aşağıdaki yöntemlerden birini uygulayabilirsiniz:

### 1. Seçenek: cPanel / Plesk / FTP Hosting
1. Hosting kontrol panelinize (cPanel, Plesk veya FileZilla/FTP) giriş yapın.
2. `public_html` (veya `skytryazilim.com` ana web dizini) içine gidin.
3. Burada `tubagungoraslan` adında yeni bir klasör oluşturun.
4. Oluşturduğunuz `tubagungoraslan.zip` dosyasını bu klasörün içine yükleyip **Extract (Arşivi Aç)** deyin (ya da klasör içindeki dosyaları doğrudan bu klasöre aktarın).
5. Tarayıcınızdan `https://skytryazilim.com/tubagungoraslan` adresine girdiğinizde web sitesi anında yayında olacaktır!

### 2. Seçenek: GitHub Pages (skytryazilim.com)
`skytryazilim.com` GitHub Pages üzerinde barındırılıyorsa:
1. `skytryazilim.com` web sitesinin GitHub deposunu (repository) açın.
2. Proje ana dizininde `tubagungoraslan` adlı bir klasör açın.
3. Bu klasörün içine `tubagungoraslan/` içerisindeki tüm dosyaları ve alt klasörleri ekleyin.
4. Değişiklikleri `git add .`, `git commit -m "Add tubagungoraslan website"` ve `git push` ile gönderin.
5. GitHub Pages birkaç saniye içinde derlemeyi tamamlayacak ve `https://skytryazilim.com/tubagungoraslan` adresinde yayına alacaktır.

### 3. Seçenek: Nginx / Apache VPS
1. Sunucunuzda `skytryazilim.com` kök dizinine (örneğin `/var/www/skytryazilim.com/html/`) gidin.
2. `tubagungoraslan` klasörünü kopyalayın:
   ```bash
   cp -r /path/to/tubagungoraslan /var/www/skytryazilim.com/html/tubagungoraslan
   chown -R www-data:www-data /var/www/skytryazilim.com/html/tubagungoraslan
   ```
3. Nginx veya Apache yeniden başlatmaya gerek kalmadan alt dizin hemen aktif olacaktır.

---

## 🌟 Yapılan İyileştirmeler & Özellikler

1. **Tam Navigasyon Entegrasyonu:**
   - Google Stitch çıktısındaki tüm dummy `#` ve `data-path` bağlantıları, sayfalar arası çalışan gerçek bağlantılarla (`index.html`, `hakkimda.html`, `calisma-alanlari.html`, `iletisim.html`) değiştirildi.
   - Her sayfada o an bulunulan menü öğesi görsel olarak aktif (altı çizgili / vurgulu) hale getirildi.

2. **Duyarlı Mobil Menü (Responsive Hamburger Menu):**
   - Orijinal Stitch tasarımında mobil ekranlarda gizlenen menü yerine; şık, açılır kapanır hamburger menü drawer eklendi.
   - Mobilde ekranın altındaki sabit hızlı arama ve randevu çubuğu entegre edildi.

3. **Çift Yönlü URL Uyumluluğu (Clean URLs):**
   - Hem uzantısız temiz linkler (`/tubagungoraslan/hakkimda`) hem de doğrudan dosya linkleri (`/tubagungoraslan/hakkimda.html`) çalışacak şekilde ayna (mirror) klasör yapısı ve `.htaccess` yapılandırıldı.

4. **İnteraktif Formlar:**
   - Ana sayfadaki `#hizli-randevu` formu ve İletişim sayfasındaki seans başvuru formuna kullanıcıya anlık bildirim veren teşekkür/onay kutusu (`alert banner`) eklendi.

5. **Hukuki Modallar (KVKK, Gizlilik ve Çerez):**
   - Alt bilgideki (footer) KVKK, Gizlilik Politikası ve Çerez Politikası linkleri tıklandığında sayfa yenilenmeden açılan profesyonel modal penceresi hazırlandı.

6. **İletişim & Randevu Entegrasyonu:**
   - WhatsApp butonu doğrudan hazır mesaj şablonuyla (`https://wa.me/905550000000?text=...`) bağlandı.
   - Hızlı telefon arama butonları yapılandırıldı.
   - Bursa Nilüfer kliniği için Google Haritalar yol tarifi bağlantısı eklendi.
