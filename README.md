# Kış Programı

Tek dosyalık antrenman ve beslenme takip sayfası. Bağımlılık yok, derleme yok — `index.html` tarayıcıda açılır.

## İçerik

- Haftanın 7 günü için ayrı program (merdiven intervali, sessiz devre, kuvvet A/B, adım günü)
- Hareketlerin Türkçe + İngilizce adları ve YouTube anlatım bağlantıları
- İşaretlenen hareketler `localStorage`'a tarih bazında yazılır, ertesi gün sıfırlanır
- Günlük makro hedefleri ve 5 dönüşümlü akşam öğünü

## GitHub Pages ile yayınlama

1. Yeni bir repo aç, iki dosyayı da köke yükle.
2. Settings → Pages → Source: `Deploy from a branch`, Branch: `main` / `(root)`.
3. Birkaç dakika sonra `https://<kullanıcı-adı>.github.io/<repo-adı>/` adresinde yayında.

Dosya adının `index.html` olması şart — Pages kökte onu arar. Private repo'da Pages ücretli plan ister; ücretsiz hesapta repo'yu public yap.

## Yerel kullanım

`index.html` dosyasını çift tıkla. Telefonda ana ekrana kısayol olarak ekleyebilirsin.

## Düzenleme

Program verisi `<script>` içindeki `DAYS` dizisinde, akşam öğünleri `DINNERS` dizisinde. Set/tekrar değiştirmek için sadece bu iki diziye dokunman yeterli.
