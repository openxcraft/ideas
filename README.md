# Idea Record Publication

Flat, deterministic record store. One file per record: `records/<id>.yaml`.
Indexes `index.md` and `index.json` are regenerated on every run.

## Record schema

Exactly these keys; empty fields are omitted, never placeholders. No free-text fields outside the schema. Records containing attribution, comments, notes, caveats, or internal content are non-conformant and discarded.

| field | form | allowed values / format |
|---|---|---|
| id | single line | `r-` + 12 lowercase hex (deterministic, stable across runs) |
| title | single line | free text |
| problem | single paragraph | free text |
| user | single line | free text |
| idea | single paragraph | free text |
| distinction | single line | free text |
| feasibility | enum | core-verified \| risk-known \| unverified |
| mvp_scope | bullet list | 0-8 items |
| out_of_scope | bullet list | 0-8 items; key omitted when empty |
| anchor_relation | enum | improves \| replaces \| independent |
| map_position | enum | known \| adjacent \| far |
| next_test | single line | free text |
| tags | list, 1-3 | controlled vocabulary only |

Sorting: records sort by `id`; the index also groups by `map_position` and `anchor_relation`.

## Controlled tag vocabulary

ai-ml, devtools, automation, productivity, api, data, security, privacy, consumer-app, social, media, gaming, education, health, biotech, fintech, payments, marketplace, saas, hardware, robotics, iot, energy, sustainability, mobility, logistics, communication, ar-vr
