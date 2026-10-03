# aura-nabiz

Sunucu tamamen yanıt vermezse e-posta bildirimi.

- [`.github/workflows/nabiz.yml`](.github/workflows/nabiz.yml) 10 dakikada bir, sunucunun dışından
  (GitHub'ın makinelerinden) aynı sunucudaki birkaç siteye istek atar.
- İstekler Cloudflare'i atlayıp doğrudan sunucuya gider: Cloudflare'in bot koruması GitHub'ın
  makinelerine kendi 403 sayfasını döndürüyor, o sayfa sunucu kapalıyken de gelir.
- Sitelerden **biri bile** cevap verirse (2xx/3xx) sunucu ayakta sayılır. Üç turun hiçbirinde cevap
  gelmezse iş başarısız olur ve GitHub depo sahibine e-posta gönderir.
- Site adresleri ve sunucu IP'si depoda değil, `SITELER` ve `SUNUCU_IP` secret'larında.

Bildirimi denemek için: **Actions → Sunucu nabzi → Run workflow → "deneme_hatasi" işaretli**.

Her siteyi tek tek görmek için (alarm üretmez): **Run workflow → "teshis" işaretli**.

Kapatmak için: **Actions → Sunucu nabzi → ⋯ → Disable workflow**.
