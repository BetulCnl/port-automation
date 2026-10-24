# Liman Otomasyonu

Bir limandaki yük indirme-yükleme akışını simüle eden Tkinter uygulaması. Tırlar yüklerini istif alanlarına bırakır, gemiler istif alanından yüklenip limandan ayrılır.

Hatice Reyhan Çalışkan ve Betül Canol, Kocaeli Sağlık ve Teknoloji Üniversitesi, Bilgisayar Mühendisliği (Ekim 2023). Projenin diğer kopyası: [ReyhanClskn/Port-Automation](https://github.com/ReyhanClskn/Port-Automation)

## Kurallar

- Tırlar geliş zamanına göre sıralanır. Aynı anda gelenlerde plaka numarası küçük olan önce indirir.
- İki istif alanı var, her biri 750 ton kapasiteli. Alanlar doluysa tırlar bekler.
- Gemiler geliş zamanına, aynı anda gelenler numarasına göre yüklenir.
- Bir gemi kapasitesinin en az %95'i dolunca limandan ayrılır. Vinç en fazla 20 işlem yapar.

## Arayüz

Soldaki butonlar:

- **Start Otomation**: simülasyonu ayrı bir thread'de başlatır, olayları sağdaki metin alanına yazar
- **Get Truck Info** / **Get Ship Info**: plakası girilen tırın veya geminin yük bilgisini gösterir
- **Clear Output**: metin alanını temizler
- **Exit**

## Çalıştırma

Program açılırken çalışma dizininde iki CSV dosyası arar. **Bu dosyalar repoda yok**, çalıştırmadan önce eklenmeleri gerekiyor.

`olaylar.csv` (tırlar, ilk satır başlık):

```
geliş_zamanı,tır_plakası,ülke,20_ton_adet,30_ton_adet,yük_miktarı,maliyet
```

Plaka `..._<sayı>` biçiminde olmalı; sıralama alt çizgiden sonraki sayıya göre yapılıyor.

`gemiler.csv` (gemiler, ilk satır başlık):

```
geliş_zamanı,gemi_adı,kapasite,gidecek_ülke
```

Gemi adı sütunu sayı olarak okunuyor. Dosyalar `latin-1` kodlamasıyla açılıyor.

```bash
python 220501001_Hatice_Reyhan_Caliskan_220501009_Betul_Canol.py
```

Tkinter Python ile birlikte geldiği için ek kurulum gerekmez.

## Dosyalar

- `*.py`: uygulamanın tamamı
- `*.pdf`: proje raporu
