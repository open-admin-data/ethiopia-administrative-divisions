# Ethiopia Administrative Divisions / ኢትዮጵያ



## Overview

| Item | Details |
|------|---------|
| Region | 15 |
| Zone | 107 |
| Woreda | 1,148 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-06-01 |
| Website | [openadmindata.org/et](https://openadmindata.org/et/) |
| API | [openadmindata.org/api/et](https://openadmindata.org/api/et/) |

## Browse by Region

| # | Region | Zones | Woredas | Link |
|---|----|----|----|------|
| 1 | Tigray | 6 | 75 | [Browse](divisions/tigray/) |
| 2 | Afar | 6 | 49 | [Browse](divisions/afar/) |
| 3 | Amhara | 14 | 225 | [Browse](divisions/amhara/) |
| 4 | Oromia | 22 | 349 | [Browse](divisions/oromia/) |
| 5 | Somali | 11 | 100 | [Browse](divisions/somali/) |
| 6 | Benishangul-Gumuz | 4 | 26 | [Browse](divisions/benishangul-gumuz/) |
| 7 | Central Ethiopia | 10 | 69 | [Browse](divisions/central-ethiopia/) |
| 8 | South Ethiopia | 12 | 93 | [Browse](divisions/south-ethiopia/) |
| 9 | South West Ethiopia | 6 | 59 | [Browse](divisions/south-west-ethiopia/) |
| 10 | Gambela | 4 | 15 | [Browse](divisions/gambela/) |
| 11 | Harari | 1 | 9 | [Browse](divisions/harari/) |
| 12 | Addis Ababa | 1 | 11 | [Browse](divisions/addis-ababa/) |
| 13 | Dire Dawa | 2 | 13 | [Browse](divisions/dire-dawa/) |
| 14 | Sidama | 5 | 37 | [Browse](divisions/sidama/) |
| 15 | Contested | 3 | 18 | [Browse](divisions/contested/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 15 region records |
| [all-zone.json](data/all-zone.json) | JSON | All 107 zone records |
| [all-woreda.json](data/all-woreda.json) | JSON | All 1,148 woreda records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['zone']} zones")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=zone, 3=woreda |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{zone-slug}/
```

Woredas are listed inline in each zone's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Ethiopia Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/ethiopia-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
