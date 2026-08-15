# Nozu API

[English](README.md) | **Türkçe**

Ücretsiz Anime ve Manga REST API'si.

Nozu API; anime, manga, karakter, ekip, seslendirme sanatçısı, stüdyo, ilişkiler, öneriler ve herkese açık kullanıcı verilerini basit bir REST API üzerinden sunar.

🌐 **Web Sitesi:** https://nozu.me  
📚 **API Dokümantasyonu:** https://nozu.me/api  
🔗 **Temel API Adresi:** `https://nozu.me/api/v1`  
📄 **OpenAPI:** [openapi.json](openapi.json)

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
- Güncel sezon verileri
- Gelişmiş arama ve filtreleme
- Otomatik tamamlama
- Rastgele anime veya manga
- Herkese açık kullanıcı profilleri ve listeleri
- JSON yanıtları
- OpenAPI tanımı
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

### Güncel Sezon

```http
GET https://nozu.me/api/v1/season-popular
```

### Rastgele

```http
GET https://nozu.me/api/v1/random
```

---

## Temel Endpointler

| Endpoint | Açıklama |
|---|---|
| `GET /search` | Anime ve manga arama |
| `GET /discover` | Anime ve manga keşfetme |
| `GET /trending` | Trend içerikleri getirir |
| `GET /popular` | Popüler içerikleri getirir |
| `GET /season-popular` | Güncel sezonun popüler yapımlarını getirir |
| `GET /latest` | Son eklenen içerikleri getirir |
| `GET /random` | Rastgele içerik getirir |
| `GET /autocomplete` | Arama otomatik tamamlama |
| `GET /anime/{slug}` | Anime detaylarını getirir |
| `GET /manga/{slug}` | Manga detaylarını getirir |
| `GET /recommendations/{slug}` | Önerileri getirir |
| `GET /studios` | Stüdyoları listeler |
| `GET /studios/{slug}` | Stüdyo detaylarını getirir |
| `GET /people` | Kişileri listeler |
| `GET /people/{slug}` | Kişi detaylarını getirir |
| `GET /characters/{slug}` | Karakter detaylarını getirir |
| `GET /users/{username}` | Herkese açık kullanıcı profilini getirir |

Tüm endpointler, parametreler ve veri şemaları için resmî dokümantasyona veya OpenAPI dosyasına bakabilirsin.

---

## JavaScript Örneği

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/search?type=anime&q=naruto'
);

const data = await response.json();

console.log(data);
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

## Örnekler

Detaylı kullanım örnekleri:

- [JavaScript](examples/javascript.md)
- [Python](examples/python.md)
- [PHP](examples/php.md)
- [Flutter / Dart](examples/flutter.md)

---

## OpenAPI

OpenAPI tanımı bu repoda bulunmaktadır:

[openapi.json](openapi.json)

Canlı OpenAPI çıktısı:

https://nozu.me/api/v1/openapi.json

---

## Kimlik Doğrulama

Nozu API'nin public endpointleri için API anahtarı gerekmez.

---

## İstek Limiti

Public API şu anda:

```text
IP başına dakikada 60 istek
```

uygulanmasını destekler.

Uygulamaların mümkün olduğu durumlarda yanıtları önbelleğe alması ve gereksiz tekrar eden isteklerden kaçınması önerilir.

---

## Dokümantasyon

Tüm API dokümantasyonu:

https://nozu.me/api

---

## Nozu Hakkında

Nozu; anime, manga, karakter, seslendirme sanatçıları, stüdyolar ve ilişkili içeriklerin keşfedilebildiği Türkçe bir anime ve manga veritabanıdır.

Nozu ayrıca geliştiricilerin anime ve manga verilerini web sitelerine, mobil uygulamalara, botlara ve diğer projelere entegre edebilmesi için herkese açık bir REST API sunar.

🌐 https://nozu.me

---

## Diller

- [English](README.md)
- [Türkçe](README_TR.md)
