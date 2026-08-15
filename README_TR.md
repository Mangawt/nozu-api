# README_TR.md

# Nozu API

[English](README.md) | **Türkçe**

Ücretsiz Anime ve Manga REST API'si.

Nozu API; anime, manga, karakter, ekip, seslendirme sanatçısı, stüdyo, ilişkiler ve öneriler gibi verileri basit bir REST API üzerinden sunar.

🌐 **Web Sitesi:** https://nozu.me  
📚 **API Dokümantasyonu:** https://nozu.me/api  
🔗 **Temel API Adresi:** `https://nozu.me/api/v1`

---

## Özellikler

- Anime veritabanı
- Manga veritabanı
- Karakterler
- Ekip ve seslendirme sanatçıları
- Stüdyolar
- İlişkili yapımlar
- Öneriler
- Trend anime ve mangalar
- Popüler anime ve mangalar
- Gelişmiş arama
- JSON yanıtları
- Public endpointler için API anahtarı gerekmez

---

## Hızlı Başlangıç

### Arama

```http
GET https://nozu.me/api/v1/search?type=anime&q=naruto
```

### Son Eklenenler

```http
GET https://nozu.me/api/v1/latest
```

### Trendler

```http
GET https://nozu.me/api/v1/trending
```

### Popüler

```http
GET https://nozu.me/api/v1/popular
```

---

## JavaScript Örneği

```javascript
fetch('https://nozu.me/api/v1/search?type=anime&q=naruto')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

---

## Yanıt Formatı

```json
{
  "success": true,
  "data": [],
  "meta": {
    "current_page": 1,
    "per_page": 24,
    "total": 120,
    "last_page": 5
  },
  "links": {
    "next": "..."
  }
}
```

---

## Kimlik Doğrulama

Nozu API'nin public endpointleri için API anahtarı gerekmez.

---

## Dokümantasyon

Tüm endpointler, parametreler ve kullanım örnekleri için:

https://nozu.me/api

---

## Nozu Hakkında

Nozu; kullanıcıların anime, manga, karakter, seslendirme sanatçıları, stüdyolar ve ilişkili içerikleri keşfetmesini sağlayan Türkçe bir anime ve manga veritabanıdır.

🌐 https://nozu.me

---

## Diller

- [English](README.md)
- [Türkçe](README_TR.md)
