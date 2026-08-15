# Nozu API — Flutter / Dart Examples

[Nozu](https://nozu.me) provides a free Anime & Manga REST API.

**Base URL**

```text
https://nozu.me/api/v1
```

Public endpoints do not require an API key.

---

## Install HTTP Package

Add the `http` package to your Flutter project:

```bash
flutter pub add http
```

Then import it:

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';
```

---

## Search Anime

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> searchAnime() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/search',
  ).replace(
    queryParameters: {
      'type': 'anime',
      'q': 'naruto',
    },
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Search Manga

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> searchManga() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/search',
  ).replace(
    queryParameters: {
      'type': 'manga',
      'q': 'berserk',
    },
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Advanced Search

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> advancedSearch() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/search',
  ).replace(
    queryParameters: {
      'type': 'anime',
      'q': 'jujutsu',
      'genre': 'Aksiyon',
      'year': '2020',
      'sort': 'popularity',
      'per_page': '12',
    },
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Latest

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getLatest() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/latest',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Trending

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getTrending() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/trending',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Popular

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getPopular() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/popular',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Current Season Popular Anime

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getSeasonPopular() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/season-popular',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Discover

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> discover() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/discover',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Random Anime or Manga

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getRandom() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/random',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Autocomplete

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> autocomplete(String query) async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/autocomplete',
  ).replace(
    queryParameters: {
      'q': query,
    },
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Anime Details

Replace `example-slug` with a valid Nozu anime slug.

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getAnime(String slug) async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/anime/$slug',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Anime Details With Relations

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getAnimeDetails(String slug) async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/anime/$slug',
  ).replace(
    queryParameters: {
      'include': 'characters,relations,staff',
    },
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Manga Details

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getManga(String slug) async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/manga/$slug',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Recommendations

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getRecommendations(
  String slug,
) async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/recommendations/$slug',
  ).replace(
    queryParameters: {
      'limit': '12',
    },
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Studios

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getStudios() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/studios',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## People

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getPeople() async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/people',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Public User Profile

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> getUserProfile(
  String username,
) async {
  final uri = Uri.parse(
    'https://nozu.me/api/v1/users/$username',
  );

  final response = await http.get(uri);

  final data = jsonDecode(response.body);

  print(data);
}
```

---

## Recommended API Service

For larger Flutter projects, it is better to keep API calls inside a service class.

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

class NozuApi {
  static const String baseUrl =
      'https://nozu.me/api/v1';

  Future<Map<String, dynamic>> searchAnime(
    String query,
  ) async {
    final uri = Uri.parse(
      '$baseUrl/search',
    ).replace(
      queryParameters: {
        'type': 'anime',
        'q': query,
      },
    );

    final response = await http.get(
      uri,
      headers: {
        'Accept': 'application/json',
      },
    );

    final dynamic decoded =
        jsonDecode(response.body);

    if (response.statusCode < 200 ||
        response.statusCode >= 300) {
      final message =
          decoded is Map<String, dynamic>
              ? decoded['message']
              : null;

      throw Exception(
        message ??
            'Nozu API error: ${response.statusCode}',
      );
    }

    return decoded as Map<String, dynamic>;
  }
}
```

Usage:

```dart
final api = NozuApi();

final result = await api.searchAnime(
  'Naruto',
);

print(result);
```

---

## Rate Limit

The public API currently allows:

```text
60 requests per minute per IP
```

Mobile applications should cache responses where appropriate and avoid unnecessary repeated requests.

---

## Documentation

Full API documentation:

https://nozu.me/api

OpenAPI specification:

https://nozu.me/api/v1/openapi.json

Website:

https://nozu.me
