# Nozu API

**English** | [Türkçe](README_TR.md)

Free Anime & Manga REST API.

Nozu API provides anime, manga, characters, staff, voice actors, studios, relations, recommendations and public user data through a simple REST API.

🌐 **Website:** https://nozu.me  
📚 **API Documentation:** https://nozu.me/api  
🔗 **Base URL:** `https://nozu.me/api/v1`  
📄 **OpenAPI:** [openapi.json](openapi.json)

---

## Features

- Anime database
- Manga database
- Characters
- Staff and voice actors
- Studios
- Relations
- Recommendations
- Trending anime and manga
- Popular anime and manga
- Current season data
- Advanced search and filtering
- Autocomplete
- Random media
- Public user profiles and lists
- JSON responses
- OpenAPI specification
- No API key required for public endpoints

---

## Quick Start

### Search

```http
GET https://nozu.me/api/v1/search?type=anime&q=naruto
```

### Latest

```http
GET https://nozu.me/api/v1/latest
```

### Trending

```http
GET https://nozu.me/api/v1/trending
```

### Popular

```http
GET https://nozu.me/api/v1/popular
```

### Current Season

```http
GET https://nozu.me/api/v1/season-popular
```

### Random

```http
GET https://nozu.me/api/v1/random
```

---

## Main Endpoints

| Endpoint | Description |
|---|---|
| `GET /search` | Search anime and manga |
| `GET /discover` | Discover media |
| `GET /trending` | Get trending media |
| `GET /popular` | Get popular media |
| `GET /season-popular` | Get popular titles from the current season |
| `GET /latest` | Get latest media |
| `GET /random` | Get random media |
| `GET /autocomplete` | Search autocomplete |
| `GET /anime/{slug}` | Get anime details |
| `GET /manga/{slug}` | Get manga details |
| `GET /recommendations/{slug}` | Get recommendations |
| `GET /studios` | List studios |
| `GET /studios/{slug}` | Get studio details |
| `GET /people` | List people |
| `GET /people/{slug}` | Get person details |
| `GET /characters/{slug}` | Get character details |
| `GET /users/{username}` | Get a public user profile |

For the complete endpoint list, parameters and schemas, see the official documentation or OpenAPI specification.

---

## JavaScript Example

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/search?type=anime&q=naruto'
);

const data = await response.json();

console.log(data);
```

---

## Response Format

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

## Examples

Detailed usage examples are available for:

- [JavaScript](examples/javascript.md)
- [Python](examples/python.md)
- [PHP](examples/php.md)
- [Flutter / Dart](examples/flutter.md)

---

## OpenAPI

The OpenAPI specification is available in this repository:

[openapi.json](openapi.json)

Live OpenAPI specification:

https://nozu.me/api/v1/openapi.json

---

## Authentication

Public Nozu API endpoints do not require an API key.

---

## Rate Limit

The public API currently allows:

```text
60 requests per minute per IP
```

Applications should cache responses where appropriate and avoid unnecessary repeated requests.

---

## Documentation

Complete documentation:

https://nozu.me/api

---

## About Nozu

Nozu is a Turkish anime and manga database designed to help users discover anime, manga, characters, voice actors, studios and related content.

Nozu also provides a public REST API that developers can use to integrate anime and manga data into websites, mobile apps, bots and other projects.

🌐 https://nozu.me

---

## Languages

- [English](README.md)
- [Türkçe](README_TR.md)
