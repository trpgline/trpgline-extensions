# Call of Cthulhu Character Extensions

This directory contains character extensions for Call of Cthulhu.

## Extension Types

- **trait**: Character traits or quirks
- **skill**: Custom skills or skill specializations
- **occupation**: Custom occupations
- **background**: Character background elements
- **ability**: Special abilities
- **equipment**: Custom equipment or artifacts

## Extension Format

Call of Cthulhu extensions should include skill values and sanity-related mechanics:

```json
{
  "name": "Example Trait",
  "version": "1.0.0",
  "system": "call-of-cthulhu",
  "description": "An example character trait",
  "author": "Author Name",
  "type": "trait",
  "data": {
    "effect": "Description of the trait's effect",
    "mechanics": {
      "skills": {},
      "sanity": 0
    }
  }
}
```

## Examples

See the `extensions/` directory for example character extensions.
