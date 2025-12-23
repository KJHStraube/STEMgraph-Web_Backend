# JSON structure: Graph metadata

**Type:** `JSON`

## Properties

| Field | Type | Multiplicity | Description |
|-------|------|--------------|-------------|
| `id` | String | 1 | The URL where the graph was generated. |
| `generatedAt` | DateTime | 1 | The timestamp when the graph was created. |
| `generatedBy` | Organization | 1 | Who created this specific graph from raw data. |
| `nodes` | Exercise | 1-n | The metadata of each exercise in the graph. |
| `links` | Link | 1-n | The edges of the graph showing exercise's dependencies. |

## structure of `generatedBy`

| Field | Type | Multiplicity | Description |
|-------|------|--------------|-------------|
| `name` | String | 1 | The creator's name. |
| `url` | String | 1 | The creator's homepage. |

### Example

```json
{
  "id": "https://stemgraph-api.boekelmann.net/",
  "generatedAt": "2025-12-18T11:13:21.238404Z",
  "generatedBy": {
    "name": "STEMgraph",
    "url": "https://github.com/STEMgraph/"
  },
  "nodes": [

  ],
  "links": [

  ]
}
