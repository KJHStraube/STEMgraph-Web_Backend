# JSON Structure: STEMgraph Repository Metadata

**Type:** `https://schema.org/LearningResource`

The metadata is placed on top of the exercise document between `<!---` and `--->`. Take care that there are **three** dashes instead of two as usual for HTML comments.

## Properties

| Field | Type | Multiplicity | Description |
|-------|------|--------------|-------------|
| `id` | String | 1 | The exercise's UUID. |
| `author` | String | 1-n | The exercise's author(s). |
| `depends_on` | String | 0-n | Exercises this one is based on. |
| `first_used` | Date | 1 | The day the exercise was first used. |
| `keywords` | String | 0-n | Tags describing the exercise's content. |
| `teaches` | String | 1 | The competency a person taking this exercise is expected to learn. |
| `title` | String | 1 | The exercise's name or title. |

### Comments

- The elements of the `depends_on` field can be either specific exercise UUIDs or a reference to a named skill which a required exercise `teaches`. 
- If more than one dependency is given, all dependencies are required for this exercise. 
- If a named skill is referenced, any one exercise which `teaches` this skill is sufficient as a requirement.
- The skill which an exercise `teaches` should be a short description, e.g. "assembly introduction" or "C basic types".

---

- It's not clear if the field `first_used` really is important. Maybe a field `published_at` would be more meaningful.

### Example

```json
{
  "id": "f87c7e89-ece7-4c55-af54-16a3b3b7435f",
  "author": "Stephan Bökelmann",
  "depends_on": [
    "302c98a7-cbea-435c-ada2-bbf7538429a2",
    "81f2e303-d35c-4857-9cb7-190e3c5372b0",
    "assembly introduction"
  ],
  "first_used": "2025-06-05",
  "keywords": ["C Compiler", "Inline Assembly", "Syscall", "Objdump", "Locals and Globals", "Primitive Types"],
  "teaches": "C basic types",
  "title": "C Compiler: Working with Primitive Types and Inspecting Binaries"
}
