# JSON Structure: Exercise

**Type:** `JSON`

## Properties of the node part of the exercise

| Field | Type | Multiplicity | Description |
|-------|------|--------------|-------------|
| `id` | String | 1 | The exercise's UUID. |
| `author` | String | 1-n | The name(s) of the exercise's author(s). |
| `keywords` | String | 0-n | Tags describing the exercise's content. |
| `learningResourceType` | String | 1 | The kind of exercise, e.g. workshop, handout or just exercise. |
| `publishedAt` | Date | 1 | The date the exercise was published. |
| `teaches` | String | 1 | The competency a person taking this exercise is expected to learn. |
| `title` | String | 1 | The exercise's name or title. |

## Properties of the link part(s) of the exercise

| Field | Type | Multiplicity | Description |
|-------|------|--------------|-------------|
| `source` | String | 1-n | The UUID of a required exercise. |
| `target` | String | 1 | This exercise's UUID. |

### Comments

- If the `source` of a link is a list of more than one exercise, any one exercise in the list `teaches` this exercise's skill and is sufficient as a requirement.

### Example

```json
{
  "id": "f87c7e89-ece7-4c55-af54-16a3b3b7435f",
  "author": "Stephan Bökelmann",
  "dependsOn": [
    "302c98a7-cbea-435c-ada2-bbf7538429a2",
    "81f2e303-d35c-4857-9cb7-190e3c5372b0",
    [
      "718193ef-11a1-408d-af23-4b10c24d490d",
      "99787eda-617a-4a68-b9a4-d60ec5c5c303"
    ]
  ],
  "keywords": [
    "C Compiler",
    "Inline Assembly",
    "Syscall",
    "Objdump",
    "Locals and Globals",
    "Primitive Types"
  ],
  "learningResourceType": "Exercise",
  "publishedAt": "2025-06-05",
  "teaches": "C basic types",
  "title": "C Compiler: Working with Primitive Types and Inspecting Binaries"
}

```json
{
  {
    "source": "302c98a7-cbea-435c-ada2-bbf7538429a2",
    "target": "f87c7e89-ece7-4c55-af54-16a3b3b7435f"
  },
  {
    "source": "81f2e303-d35c-4857-9cb7-190e3c5372b0",
    "target": "f87c7e89-ece7-4c55-af54-16a3b3b7435f"
  },
  {
    "source": [
      "718193ef-11a1-408d-af23-4b10c24d490d",
      "99787eda-617a-4a68-b9a4-d60ec5c5c303"
    ],
    "target": "f87c7e89-ece7-4c55-af54-16a3b3b7435f"
  }
}
