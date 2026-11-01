# localreel-format

Versioned data formats shared by the LocalReel crates.

This crate has **no I/O** and no async runtime. It only defines the JSON/values
that move between components:

- `Backup` — portable sources + playback state export (`version = 2`).
- `ArtifactKind` and artifact name helpers — deterministic, filesystem-safe
  names for generated thumbnails, transcodes and HLS packages.
- `FormatError` — validation errors that callers map to API/CLI errors.

## Layout

```text
src/lib.rs   format types, validation, artifact naming
```

## Versioning

`Backup.version` is checked strictly. Bump it only with a migration path in
`localreel-core`; never reinterpret an unknown version silently.

## License

TBD by the repository owner.
