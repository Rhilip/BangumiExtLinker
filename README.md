# BangumiExtLinker

Try to associate the animation entries in [Bangumi 番组计划](https://bgm.tv/) with the corresponding IDs on other metadata-providing websites (aka **Info Site**) such as [Douban](https://movie.douban.com/), [IMDb](https://www.imdb.com/) et al.

**All data comes from the Internet and is for learning purposes only!**

## Update Status

- Last update at: `2025-02-04 12:54:04` (CET, UTC+01:00)
- Last data summary:

| Info Site | Count |
|:----:|----:|
| Bangumi | 22547 |
| Douban | 9835 |
| Bilibili | 3332 |
| AniDB | 10221 |
| MyAnimeList | 11861 |
| TMDB | 4088 |
| IMDb | 4779 |
| TheTVDB | 2017 |
| Wikidata | 2781 |

## Note

1. Schema File for [anime_map.json](/data/anime_map.json) ([Github Pages](https://rhilip.github.io/BangumiExtLinker/data/anime_map.json))

```json5
[
    {
        // Content from bangumi/Archive Subject ( type=2 && nsfw=0 )
        "name": "葬送のフリーレン",
        "name_cn": "葬送的芙莉莲",
        "date": "2023-09",
        "bgm_id": "400602",
        // The Linked Id in other metadata-providing websites ( The following field will not exist when mis-match )
        "douban_id": "36093351",          // From PtGen (by info), self-scrape (by info)
        "bili_id": "md21087073",          // From bangumi-data (by bgm_id)
        "anidb_id": "17617",              // From anime-offline-database (by info), self-scrape (by info)
        "mal_id": "52991",                // From anime-offline-database (by info), self-scrape (by info)
        "tmdb_id": "tv/209867/season/1",  // From TMDB api (by search and imdb_id)
        "imdb_id": "tt22248376",          // From Ptgen (by douban_id), TMDB api (by tmdb_id)
        "tvdb_id": "424536",              // From TMDB api (by tmdb_id)
        "wikidata_id": "Q56551019"        // From TMDB api (by tmdb_id), WikiData Query Service (by info, douban_id, imdb_id, et al)
    },
    // More.....
]
```

2. **`Link Format`** follow the description in the table below: 

| Info Site | Link Format |
|:----:|:----|
| Bangumi | `https://bgm.tv/subject/{bgm_id:\d+}` |
| Douban | `https://movie.douban.com/subject/{douban_id:\d+}/` |
| Bilibili | `https://www.bilibili.com/bangumi/media/{bili_id:md\d+}/` |
| AniDB | `https://anidb.net/anime/{anidb_id:\d+}` |
| MyAnimeList | `https://myanimelist.net/anime/{mal_id:\d+}`
| TMDB | `https://www.themoviedb.org/{tmdb_id:tv/\d+(/season/\d+(/episode/\d+)?)?\|movie/\d+}` |
| IMDb | `https://www.imdb.com/title/{imdb_id:tt\d+}/` |
| TheTVDB | `https://thetvdb.com/dereferrer/series/{tvdb_id:\d+}` |
| Wikidata | `https://www.wikidata.org/wiki/{wikidata_id:Q\d+}` |

3. This Repo based on Bangumi ID, However different metadata-providing websites may split the same work into different entries when handling it. 
When A Bangumi entry may be split into two or more entries on other metadata-providing websites, only one of the Linked IDs will be marked, and other IDs may be ignored.

## Appreciation

| Repo | Description | License |
|:---|:---|:---:|
| [bangumi/Archive](https://github.com/bangumi/Archive) | Bangumi Wiki Archive | [CC BY-SA](https://bgm.tv/about/copyright#columnA) |
| [czy0729/Bangumi-Subject](https://github.com/czy0729/Bangumi-Subject) | Static data snapshot of Bangumi hot subject | - |
| [bangumi-data/bangumi-data](https://github.com/bangumi-data/bangumi-data) | Raw data for Japanese Anime | [CC BY 4.0](https://github.com/bangumi-data/bangumi-data#license) |
| [manami-project/anime-offline-database](https://github.com/manami-project/anime-offline-database) | A JSON based anime dataset ... | [AGPL-3.0](https://github.com/manami-project/anime-offline-database/blob/master/LICENSE) |
| [ourbits/PtGen](https://github.com/ourbits/PtGen) | The static export of the PtGen Database. | [MIT](https://github.com/ourbits/PtGen/blob/main/LICENSE) |

## License

The data in this repo is available for use under a [CC BY 4.0 license](http://creativecommons.org/licenses/by/4.0/). For works with existing copyrights, handle them in accordance with the [Fair Use](http://en.wikipedia.org/wiki/Fair_use) principle and indicate the source.