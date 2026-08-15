# Nozu API — Python Examples

[Nozu](https://nozu.me) provides a free Anime & Manga REST API.

**Base URL**

```text
https://nozu.me/api/v1
```

Public endpoints do not require an API key.

---

## Requirements

These examples use the `requests` package.

Install it with:

```bash
pip install requests
```

---

## Search Anime

```python
import requests

url = "https://nozu.me/api/v1/search"

params = {
    "type": "anime",
    "q": "naruto"
}

response = requests.get(url, params=params)
data = response.json()

print(data)
```

---

## Search Manga

```python
import requests

url = "https://nozu.me/api/v1/search"

params = {
    "type": "manga",
    "q": "berserk"
}

response = requests.get(url, params=params)
data = response.json()

print(data)
```

---

## Advanced Search

```python
import requests

url = "https://nozu.me/api/v1/search"

params = {
    "type": "anime",
    "q": "jujutsu",
    "genre": "Aksiyon",
    "year": 2020,
    "sort": "popularity",
    "per_page": 12
}

response = requests.get(url, params=params)
data = response.json()

print(data)
```

---

## Latest

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/latest"
)

print(response.json())
```

---

## Trending

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/trending"
)

print(response.json())
```

---

## Popular

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/popular"
)

print(response.json())
```

---

## Current Season Popular Anime

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/season-popular"
)

print(response.json())
```

---

## Discover

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/discover"
)

print(response.json())
```

---

## Random Anime or Manga

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/random"
)

print(response.json())
```

---

## Autocomplete

```python
import requests

params = {
    "q": "naruto"
}

response = requests.get(
    "https://nozu.me/api/v1/autocomplete",
    params=params
)

print(response.json())
```

---

## Anime Details

Replace `example-slug` with a valid Nozu anime slug.

```python
import requests

slug = "example-slug"

response = requests.get(
    f"https://nozu.me/api/v1/anime/{slug}"
)

print(response.json())
```

---

## Anime Details With Relations

```python
import requests

slug = "example-slug"

params = {
    "include": "characters,relations,staff"
}

response = requests.get(
    f"https://nozu.me/api/v1/anime/{slug}",
    params=params
)

print(response.json())
```

---

## Manga Details

```python
import requests

slug = "example-slug"

response = requests.get(
    f"https://nozu.me/api/v1/manga/{slug}"
)

print(response.json())
```

---

## Recommendations

```python
import requests

slug = "example-slug"

params = {
    "limit": 12
}

response = requests.get(
    f"https://nozu.me/api/v1/recommendations/{slug}",
    params=params
)

print(response.json())
```

---

## Studios

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/studios"
)

print(response.json())
```

---

## People

```python
import requests

response = requests.get(
    "https://nozu.me/api/v1/people"
)

print(response.json())
```

---

## Public User Profile

```python
import requests

username = "username"

response = requests.get(
    f"https://nozu.me/api/v1/users/{username}"
)

print(response.json())
```

---

## Error Handling

```python
import requests

def search_anime(query):
    url = "https://nozu.me/api/v1/search"

    params = {
        "type": "anime",
        "q": query
    }

    try:
        response = requests.get(
            url,
            params=params,
            timeout=10
        )

        response.raise_for_status()

        return response.json()

    except requests.RequestException as error:
        print(f"Nozu API error: {error}")
        raise


data = search_anime("Naruto")

print(data)
```

---

## Rate Limit

The public API currently allows:

```text
60 requests per minute per IP
```

Applications should cache responses where appropriate and avoid unnecessary requests.

---

## Documentation

Full API documentation:

https://nozu.me/api

OpenAPI specification:

https://nozu.me/api/v1/openapi.json

Website:

https://nozu.me
