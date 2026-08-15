# Nozu API — PHP Examples

[Nozu](https://nozu.me) provides a free Anime & Manga REST API.

**Base URL**

```text
https://nozu.me/api/v1
```

Public endpoints do not require an API key.

---

## Search Anime

```php
<?php

$query = urlencode('naruto');

$url = "https://nozu.me/api/v1/search?type=anime&q={$query}";

$response = file_get_contents($url);

$data = json_decode($response, true);

print_r($data);
```

---

## Search Manga

```php
<?php

$query = urlencode('berserk');

$url = "https://nozu.me/api/v1/search?type=manga&q={$query}";

$response = file_get_contents($url);

$data = json_decode($response, true);

print_r($data);
```

---

## Advanced Search

```php
<?php

$params = http_build_query([
    'type' => 'anime',
    'q' => 'jujutsu',
    'genre' => 'Aksiyon',
    'year' => 2020,
    'sort' => 'popularity',
    'per_page' => 12,
]);

$url = "https://nozu.me/api/v1/search?{$params}";

$response = file_get_contents($url);

$data = json_decode($response, true);

print_r($data);
```

---

## Latest

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/latest'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Trending

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/trending'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Popular

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/popular'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Current Season Popular Anime

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/season-popular'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Discover

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/discover'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Random Anime or Manga

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/random'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Autocomplete

```php
<?php

$query = urlencode('naruto');

$response = file_get_contents(
    "https://nozu.me/api/v1/autocomplete?q={$query}"
);

$data = json_decode($response, true);

print_r($data);
```

---

## Anime Details

Replace `example-slug` with a valid Nozu anime slug.

```php
<?php

$slug = 'example-slug';

$response = file_get_contents(
    "https://nozu.me/api/v1/anime/{$slug}"
);

$data = json_decode($response, true);

print_r($data);
```

---

## Anime Details With Relations

```php
<?php

$slug = 'example-slug';

$include = urlencode('characters,relations,staff');

$response = file_get_contents(
    "https://nozu.me/api/v1/anime/{$slug}?include={$include}"
);

$data = json_decode($response, true);

print_r($data);
```

---

## Manga Details

```php
<?php

$slug = 'example-slug';

$response = file_get_contents(
    "https://nozu.me/api/v1/manga/{$slug}"
);

$data = json_decode($response, true);

print_r($data);
```

---

## Recommendations

```php
<?php

$slug = 'example-slug';

$response = file_get_contents(
    "https://nozu.me/api/v1/recommendations/{$slug}?limit=12"
);

$data = json_decode($response, true);

print_r($data);
```

---

## Studios

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/studios'
);

$data = json_decode($response, true);

print_r($data);
```

---

## People

```php
<?php

$response = file_get_contents(
    'https://nozu.me/api/v1/people'
);

$data = json_decode($response, true);

print_r($data);
```

---

## Public User Profile

```php
<?php

$username = 'username';

$response = file_get_contents(
    "https://nozu.me/api/v1/users/{$username}"
);

$data = json_decode($response, true);

print_r($data);
```

---

## cURL Example

For production PHP applications, cURL gives you more control over requests.

```php
<?php

$url = 'https://nozu.me/api/v1/search?type=anime&q=naruto';

$curl = curl_init();

curl_setopt_array($curl, [
    CURLOPT_URL => $url,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_TIMEOUT => 10,
    CURLOPT_HTTPHEADER => [
        'Accept: application/json',
    ],
]);

$response = curl_exec($curl);

if ($response === false) {
    throw new RuntimeException(
        curl_error($curl)
    );
}

$status = curl_getinfo(
    $curl,
    CURLINFO_HTTP_CODE
);

curl_close($curl);

$data = json_decode(
    $response,
    true
);

if ($status >= 400) {
    throw new RuntimeException(
        $data['message'] ?? "HTTP error: {$status}"
    );
}

print_r($data);
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
