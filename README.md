# Kış Programı

Tek dosyalık antrenman ve beslenme takip sayfası. Bağımlılık yok, derleme yok — `index.html` doğrudan tarayıcıda açılır.

**Canlı:** https://alikrc.github.io/WorkoutPlan/

## İçerik

- Haftanın 7 günü için ayrı program: merdiven intervali (Pzt/Cum), kuvvet A/B (Sal/Cmt), sessiz devre (Çar), adım günü (Per), yürüyüş (Paz)
- Hareketlerin Türkçe + İngilizce adları ve her biri için YouTube arama bağlantısı
- Sayfa açılınca bugünün günü seçili gelir; işaretlenen hareketler `localStorage`'a tarih bazında yazılır, ertesi gün sıfırlanır
- Günlük makro hedefleri, öğün saatleri ve 5 dönüşümlü akşam öğünü — her biri için YouTube, Nefis Yemek Tarifleri ve yemek.com arama bağlantısı
- "Daha fazla tarif" bölümü: yağsız / yüksek proteinli tarif kategorileri ve hazır YouTube aramaları

## Yerel kullanım

`index.html` dosyasını çift tıkla. Telefonda ana ekrana kısayol olarak eklenebilir.

## GitHub Pages

Sayfa bu repo'dan yayınlanıyor: Settings → Pages → Source: `Deploy from a branch`, Branch: `main` / `(root)`.

`main`'e push edilen her değişiklik birkaç dakika içinde canlıya yansır. Dosya adının `index.html` olması şart — Pages kökte onu arar.

## Düzenleme

Tüm veri `index.html` içindeki `<script>` bloğunda:

- `DAYS` — günlük programlar. Her hareket şu alanları alır:
  - `n` hareket adı (Türkçe), `en` İngilizce adı (opsiyonel)
  - `d` set/tekrar/süre, `t` kısa not (opsiyonel)
  - `q` YouTube arama sorgusu (opsiyonel, verilirse oynat butonu çıkar)
- `DINNERS` — akşam öğünleri (`n` ad, `k` kalori/protein, `d` tarif, `q` YouTube araması, `s` tarif sitesi araması)
- `MORE` — "Daha fazla tarif" bağlantıları (`n` başlık, `src` kaynak, `href` adres)
- Makro hedefleri ve öğün saatleri `<section class="card">` içinde düz HTML

Set/tekrar değiştirmek için sadece `DAYS` dizisine dokunmak yeterli.
