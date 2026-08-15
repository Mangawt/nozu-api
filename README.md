# README.md

# Nozu API

**English** | [Türkçe](README_TR.md)

Free Anime & Manga REST API.

Nozu API provides anime, manga, character, staff, voice actor, studio, relation and recommendation data through a simple REST API.

🌐 **Website:** https://nozu.me  
📚 **API Documentation:** https://nozu.me/api  
🔗 **Base URL:** `https://nozu.me/api/v1`

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
- Advanced search
- JSON responses
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

---

## JavaScript Example

```javascript
fetch('https://nozu.me/api/v1/search?type=anime&q=naruto')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));
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

## Authentication

Public Nozu API endpoints do not require an API key.

---

## Documentation

For complete endpoint documentation, parameters and examples:

https://nozu.me/api

---

## About Nozu

Nozu is a Turkish anime and manga database designed to help users discover anime, manga, characters, voice actors, studios and related content.

🌐 https://nozu.me

---

## Languages

- [English](README.md)
- [Türkçe](README_TR.md)
