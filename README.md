# BangumiExtLinker

Try to associate the animation entries in [Bangumi 番组计划](https://bgm.tv/) with the corresponding IDs on other metadata-providing websites (aka **Info Site**) such as [Douban](https://movie.douban.com/), [IMDb](https://www.imdb.com/), et al.

**All data comes from the Internet and is for learning purposes only!**

## Update Status

- Last update at: `2025-02-03 10:31:13` (CET, UTC+01:00)
- Last data summary:

| Info Site | Count |
|:----:|----:|
| Bangumi | 22547 |
| Douban | 6381 |
| Bilibili | 0 |
| AniDB | 385 |
| MyAnimeList | 334 |
| TMDB | 2 |
| IMDb | 3052 |

## Note

1. Schema File for [anime_map.json](/data/anime_map.json)

```json5
[
    {
        // Content from bangumi/Archive Subject ( type=2 && nsfw=1 )
        "name": "葬送のフリーレン",
        "name_cn": "葬送的芙莉莲",
        "date": "2023-09",
        "bgm_id": "400602",
        // The Linked Id in other metadata-providing websites ( The following field will not exist when mis-match )
        "douban_id": "36093351",
        "imdb_id": "tt22248376"
    },
    // More.....
]
```

2. **`Link Format`** follow the description in the table below: 

| Info Site | Link Format |
|:----:|:----|
| Bangumi | `https://bgm.tv/subject/{bgm_id}` |
| Douban | `https://movie.douban.com/subject/{douban_id}/` |
| IMDb | `https://www.imdb.com/title/{imdb_id}/` |

3. This Repo based on Bangumi ID, However different metadata-providing websites may split the same work into different entries when handling it. 
When A Bangumi entry may be split into two or more entries on other metadata-providing websites, only one of the Linked IDs will be marked, and other IDs may be ignored.

## Appreciation

| Repo | Description | License | Work for |
|:---:|:---|:---:|:---|
| [bangumi/Archive](https://github.com/bangumi/Archive) | Bangumi Wiki Archive | [CC BY-SA](https://bgm.tv/about/copyright#columnA) | For bmg_id source |
| [czy0729/Bangumi-Subject](https://github.com/czy0729/Bangumi-Subject) | Static data snapshot of Bangumi hot subject | - | For some douban_id and match_script |
| [ourbits/PtGen](https://github.com/ourbits/PtGen) | The static export of the PtGen Database | MIT | For `douban <-> imdb` link |
