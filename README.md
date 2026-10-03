# aura-nabiz

Sunucu tamamen yanıt vermezse e-posta bildirimi.

- [`.github/workflows/nabiz.yml`](.github/workflows/nabiz.yml) 10 dakikada bir, sunucunun dışından
  (GitHub'ın makinelerinden) aynı sunucudaki birkaç siteye istek atar.
- Sitelerden **biri bile** 2xx dönerse sunucu ayakta sayılır. Üç turun hiçbirinde 2xx gelmezse iş
  başarısız olur ve GitHub depo sahibine e-posta gönderir.
- Site adresleri depoda değil, `SITELER` secret'ında.

Bildirimi denemek için: **Actions → Sunucu nabzi → Run workflow → "deneme_hatasi" işaretli**.

Her siteyi tek tek görmek için (alarm üretmez): **Run workflow → "teshis" işaretli**.

Kapatmak için: **Actions → Sunucu nabzi → ⋯ → Disable workflow**.
