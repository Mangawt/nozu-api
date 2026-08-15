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

Latest
GET https://nozu.me/api/v1/latest

Trending
GET https://nozu.me/api/v1/trending

Popular
GET https://nozu.me/api/v1/popular
