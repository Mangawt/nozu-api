# Nozu API — JavaScript Examples

[Nozu](https://nozu.me) provides a free Anime & Manga REST API.

**Base URL**

```text
https://nozu.me/api/v1
```

Public endpoints do not require an API key.

---

## Search Anime

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/search?type=anime&q=naruto'
);

const data = await response.json();

console.log(data);
```

---

## Search Manga

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/search?type=manga&q=berserk'
);

const data = await response.json();

console.log(data);
```

---

## Advanced Search

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/search?type=anime&q=jujutsu&genre=Aksiyon&year=2020&sort=popularity&per_page=12'
);

const data = await response.json();

console.log(data);
```

---

## Latest

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/latest'
);

const data = await response.json();

console.log(data);
```

---

## Trending

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/trending'
);

const data = await response.json();

console.log(data);
```

---

## Popular

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/popular'
);

const data = await response.json();

console.log(data);
```

---

## Current Season Popular Anime

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/season-popular'
);

const data = await response.json();

console.log(data);
```

---

## Discover

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/discover'
);

const data = await response.json();

console.log(data);
```

---

## Random Anime or Manga

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/random'
);

const data = await response.json();

console.log(data);
```

---

## Autocomplete

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/autocomplete?q=naruto'
);

const data = await response.json();

console.log(data);
```

---

## Anime Details

Replace `slug` with a valid Nozu anime slug.

```javascript
const slug = 'example-slug';

const response = await fetch(
    `https://nozu.me/api/v1/anime/${slug}`
);

const data = await response.json();

console.log(data);
```

---

## Anime Details With Relations

```javascript
const slug = 'example-slug';

const response = await fetch(
    `https://nozu.me/api/v1/anime/${slug}?include=characters,relations,staff`
);

const data = await response.json();

console.log(data);
```

---

## Manga Details

```javascript
const slug = 'example-slug';

const response = await fetch(
    `https://nozu.me/api/v1/manga/${slug}`
);

const data = await response.json();

console.log(data);
```

---

## Recommendations

```javascript
const slug = 'example-slug';

const response = await fetch(
    `https://nozu.me/api/v1/recommendations/${slug}?limit=12`
);

const data = await response.json();

console.log(data);
```

---

## Studios

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/studios'
);

const data = await response.json();

console.log(data);
```

---

## People

```javascript
const response = await fetch(
    'https://nozu.me/api/v1/people'
);

const data = await response.json();

console.log(data);
```

---

## Public User Profile

```javascript
const username = 'username';

const response = await fetch(
    `https://nozu.me/api/v1/users/${username}`
);

const data = await response.json();

console.log(data);
```

---

## Error Handling

```javascript
async function searchAnime(query) {
    try {
        const response = await fetch(
            `https://nozu.me/api/v1/search?type=anime&q=${encodeURIComponent(query)}`
        );

        const data = await response.json();

        if (!response.ok) {
            throw new Error(
                data.message || `HTTP error: ${response.status}`
            );
        }

        return data;
    } catch (error) {
        console.error('Nozu API error:', error);
        throw error;
    }
}

searchAnime('Naruto')
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

---

## Rate Limit

The public API currently allows:

```text
60 requests per minute per IP
```

Applications should respect the rate-limit headers and cache responses where appropriate.

---

## Documentation

Full API documentation:

https://nozu.me/api

OpenAPI specification:

https://nozu.me/api/v1/openapi.json

Website:

https://nozu.me
