# Ortak Futbolcu (kendi sunucunda)

## Çalıştırma
    npm install
    ANTHROPIC_API_KEY=sk-ant-... npm start     # Claude ile doğrulama
    npm start                                  # yalnızca players.json ile doğrulama

Tarayıcıda http://localhost:3000 aç, bir oyuncu "Oda kur" der, diğeri kodu girer.
Node 18 veya üstü gerekir. İnternete açmak için Render, Railway veya Fly.io gibi
WebSocket destekleyen bir servise yükle (PORT ortam değişkenini otomatik okur).

## Doğrulama
1. Cevap `players.json` içinde varsa orası belirler (yanlış cevap riski yok).
2. Yoksa ve `ANTHROPIC_API_KEY` tanımlıysa Claude API'ye sorulur (model: MODEL ortam değişkeni, varsayılan claude-sonnet-5-5).
3. İkisi de yoksa cevap yanlış sayılır.

`players.json` biçimi: "Oyuncu Adı": ["Takım1", "Takım2", ...]. Takım adları server.js
içindeki listedeki yazımla birebir aynı olmalı. Dosyada 90 civarı oyuncu var; kendi
veritabanınla genişlet.
