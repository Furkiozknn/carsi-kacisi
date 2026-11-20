# Sürüm notları

## v2.1 · Kasım 2026

Oynanış, kayıt anahtarları ve oyunun adresi değişmedi; eski kayıtlarla açılır.

**Yenilikler**
- **Başarımlar:** 9 hedef (ilk yakalama, üç yıldız, lonca işaretleri, tezgâh zinciri, günlük meydan okuma, Çarşı Turu'nda 300 m...). Ana menüde "Başarımlar" düğmesi; açılınca küçük bir bildirim çıkar. Daha önce ilerleyen oyuncular için uygun olanlar sessizce açık gelir. Kayıt: `arena.carsi.ach` (yalnız tarayıcıda).
- **Sürüm etiketi ve "Yenilikler" penceresi:** ana menüde `v2.1 · Kasım 2026` ve Yenilikler düğmesi; Esc ile kapanır.
- **"Diğer oyunlar" bağlantısı:** ana menüden https://furkiozknn.github.io/ adresine.

**Düzeltmeler**
- Tarayıcı her açılışta `favicon.ico` isteyip 404 alıyordu; sekme simgesi eklendi.
- `theme-color` eklendi (mobil tarayıcı çubuğu oyunun rengine uyar).
- Sayfa açıklaması ve Open Graph kartı İngilizceydi ama sayfa dili Türkçeydi; açıklama Türkçe yapıldı, Twitter kartı alanları ve paylaşım görseli açıklaması eklendi.
- Bulunamayan adresler için `404.html` eklendi (oyuna ve merkez sayfaya bağlantı).
- `tools/smoke.mjs` ve `tools/gate.mjs`: Playwright'ın kendi tarayıcısı yoksa `PW_EXECUTABLE=<yol>` ile yerel bir Chromium tabanlı tarayıcı kullanılabilir.
