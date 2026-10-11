# Kış Programı

Tek dosyalık antrenman ve beslenme takip sayfası. Bağımlılık yok, derleme yok — `index.html` doğrudan tarayıcıda açılır.

**Canlı:** https://alikrc.github.io/WorkoutPlan/

## İçerik

- Haftada 3 gün (Pzt/Çar/Cum) dönüşümlü iki seans: **A = squat + dambıl RDL**, **B = şınav + barfiks**. Seans 18.30'da, akşam yemeğinden (19.30) önce: 2 dk ısınma + A için 10 dk, B için 8 dk. Tek haftalarda A–B–A, çift haftalarda B–A–B. Sal/Per 5 dk barfiks rutini, Cmt/Paz dinlenme
- Hareketlerin Türkçe + İngilizce adları ve her biri için YouTube arama bağlantısı
- Sayfa açılınca bugünün günü seçili gelir; işaretlenen hareketler `localStorage`'a tarih bazında yazılır, ertesi gün sıfırlanır
- Günlük makro hedefleri ve her gün aynı olan sabit öğünler (13.00 öğle, akşam 100 g peynir, gece 250 ml süt), üstüne 11 küçük akşam yemeği seçeneği (6 tavuklu, 3 kıymalı, 2 baklagil). Her seçenekte gün toplamı sabitlerle birlikte hesaplanır; her biri için YouTube, Nefis Yemek Tarifleri ve yemek.com arama bağlantısı
- "Daha fazla tarif" bölümü: yağsız / yüksek proteinli tarif kategorileri ve hazır YouTube aramaları

## Yerel kullanım

`index.html` dosyasını çift tıkla. Telefonda ana ekrana kısayol olarak eklenebilir.

## GitHub Pages

Sayfa bu repo'dan yayınlanıyor: Settings → Pages → Source: `Deploy from a branch`, Branch: `main` / `(root)`.

`main`'e push edilen her değişiklik birkaç dakika içinde canlıya yansır. Dosya adının `index.html` olması şart — Pages kökte onu arar.

## Düzenleme

Tüm veri `index.html` içindeki `<script>` bloğunda:

- `WARM_LOW`, `WARM_UP`, `A_MAIN`, `B_MAIN`, `HANG` — hareket blokları (ısınmalar, A/B seansları, Sal/Per barfiks rutini). Her hareket şu alanları alır:
  - `n` hareket adı (Türkçe), `en` İngilizce adı (opsiyonel)
  - `d` set/tekrar/süre, `t` kısa not (opsiyonel)
  - `q` YouTube arama sorgusu (opsiyonel, verilirse oynat butonu çıkar)
- `A`, `B` — seansların başlık/süre bilgisi ve ilerleme notu; `DAYS` bu ikisini haftanın günlerine dağıtır (tek/çift hafta düzeni `isoWeek` ile hesaplanır)
- `FIXED` — her gün aynı olan sabit öğünler (`t` saat, `n` ad, `d` içerik, `kcal`, `p` protein g). Toplamı akşam seçeneklerinin gün toplamına otomatik eklenir
- `DINNERS` — akşam seçenekleri, gruplar halinde (`g` grup başlığı, `items` listesi). Her öğe: `n` ad, `kcal` ve `p` (yalnızca tabak, sabit peynir hariç), `d` tarif, `q` YouTube araması, `s` tarif sitesi araması
- `MORE` — "Daha fazla tarif" bağlantıları (`n` başlık, `src` kaynak, `href` adres)
- Günlük makro hedefleri (kcal, protein, yağ, karbonhidrat) `<section class="card">` içinde düz HTML

Set/tekrar değiştirmek için ilgili bloğun (`A_MAIN`, `B_MAIN` vb.) `d` alanını düzenlemek yeterli.
