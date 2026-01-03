# Data Acknowledgements

This document credits the data sources used across all collections in this repository.

---

## API-Sourced Data

The following services were accessed via their **official APIs** with proper rate limiting and attribution:

### MusicBrainz API

- https://musicbrainz.org/
- **API endpoint:** `musicbrainz.org/ws/2`
- **Used for:** Song metadata (duration, recording IDs, release IDs)
- **Licence:** CC0 (public domain dedication)
- **Files enriched:** 99 songs in `examples/songs/`

### Cover Art Archive API

- https://coverartarchive.org/
- **API endpoint:** `coverartarchive.org/release/{mbid}`
- **Used for:** Album cover images
- **Licence:** CC BY-NC-SA 3.0 (non-commercial, share-alike)
- **Files enriched:** 74 songs with cover art in `examples/songs/`

### Open Library API

- https://openlibrary.org/
- **API endpoint:** `openlibrary.org/search.json`
- **Used for:** Book metadata (page counts, edition counts, ISBNs, descriptions, ratings, cover images)
- **Licence:** Open data (part of Internet Archive)
- **Files enriched:** 92 books in `examples/books/`

### Wikipedia MediaWiki API

- https://en.wikipedia.org/w/api.php
- **API endpoint:** `en.wikipedia.org/w/api.php`
- **Used for:** Tracing broken Wikimedia image URLs back to Wikipedia articles and finding current image URLs
- **Licence:** CC BY-SA 3.0 / CC BY-SA 4.0
- **Files fixed:** 79 broken image URLs across books, games, movies, songs, and TV shows

### REST Countries API

- https://restcountries.com/
- **API endpoint:** `restcountries.com/v3.1/independent`
- **Used for:** Country metadata (names, capitals, regions, population, area, borders, languages, currencies, flags)
- **Licence:** MPL-2.0 (Mozilla Public Licence 2.0)
- **Files created:** 250 countries and 6 regions in `examples/countries/`

### Wikidata SPARQL API

- https://query.wikidata.org/
- **API endpoint:** `query.wikidata.org/sparql`
- **Used for:** Board game and composer metadata (names, dates, nationalities, notable works)
- **Licence:** CC0 (public domain dedication)
- **Files created:**
  - 50 board games and 8 categories in `examples/boardgames/`
  - 93 composers and 4 eras in `examples/composers/`

---

## Planned API Integration

The following APIs have integration scripts ready but have **not yet been used**:

### The Movie Database (TMDB)

- https://www.themoviedb.org/
- **Status:** Script created (`scripts/enrich_tmdb.py`), awaiting API key
- **Planned for:** Movies and TV shows metadata and poster images
- **Required attribution:** "This product uses the TMDB API but is not endorsed or certified by TMDB."

---

## Image Attribution

Each image includes individual licence information in its `attribution` field:

```json
{
  "attribution": {
    "source": "Cover Art Archive",
    "licence": "CC BY-NC-SA 3.0",
    "licenceUrl": "https://wiki.musicbrainz.org/Cover_Art_Archive",
    "sourceUrl": "https://musicbrainz.org/release/..."
  }
}
```

### Licence Types Used

| Licence | Description |
|---------|-------------|
| `CC0` | Public domain, no restrictions |
| `CC BY-NC-SA 3.0` | Attribution, non-commercial, share-alike |
| `MPL-2.0` | Mozilla Public Licence 2.0 |
| `open-data` | Open Library's open data policy |
| `cc-by-sa-3.0` | Wikipedia/Wikimedia content |
| `public-domain` | National flags and similar content |
| `fair-use` | Limited educational use (legacy images) |

---

## Data Collection Principles

1. **API-First**: Official APIs used where available
2. **Transparency**: This document accurately reflects what was actually used
3. **Attribution**: Every API-sourced item includes source attribution
4. **Rate Limiting**: All API access respects published rate limits
5. **Non-Commercial**: All usage complies with non-commercial licence terms

---

## Per-Collection Status

| Collection | API Used | Manual/Wikipedia |
|------------|----------|------------------|
| `examples/songs/` | ✅ MusicBrainz, Cover Art Archive | ✅ Wikipedia |
| `examples/books/` | ✅ Open Library | ✅ Wikipedia |
| `examples/movies/` | ❌ (TMDB planned) | ✅ Wikipedia |
| `examples/tv/` | ❌ (TMDB planned) | ✅ Wikipedia |
| `examples/games/vc/` | ❌ | ✅ Wikipedia |
| `examples/countries/` | ✅ REST Countries | ❌ |
| `examples/boardgames/` | ✅ Wikidata | ✅ Wikipedia |
| `examples/composers/` | ✅ Wikidata | ✅ Wikipedia |
| `collections/retro/` | ❌ | ✅ Wikipedia, YouTube links |

---

## Contact

For questions about data usage or attribution, please open an issue in this repository.
