# localreel-format

Versioned data formats shared by the LocalReel crates.

This crate has no I/O and no async runtime. It defines the JSON values and
helpers that move between components:

- `Backup` — portable sources + playback state export (`version = 2`).
- `ArtifactKind` and artifact name helpers — deterministic, filesystem-safe
  names for generated thumbnails, transcodes and HLS packages.
- `FormatError` — validation errors that callers map to API/CLI errors.

## Layout

```text
src/lib.rs   format types, validation, artifact naming
```

## Versioning

`Backup.version` is validated strictly. A new version requires a migration path
in the consuming crate; an unknown version is never reinterpreted silently.

## Where this fits

This repository is a **component**: a leaf crate. Installers, downloads and the
composed product live in the
[`LocalReel`](https://github.com/LocalReel/LocalReel) product repository.

## License

Apache-2.0 — see [`LICENSE`](LICENSE). Copyright 2026 LocalReel contributors.

---

## 简体中文

LocalReel 各组件共享的版本化数据格式。

本 crate 不做 I/O，也不依赖异步运行时，只定义组件之间传递的 JSON 结构与辅助
函数：`Backup`（来源 + 播放状态的便携导出，`version = 2`）、`ArtifactKind`
（缩略图、转码、HLS 产物的确定性文件名）与 `FormatError`（调用方映射为
API/CLI 错误）。

`Backup.version` 严格校验：新版本必须在调用方提供迁移路径，未知版本不会被
静默解释。

本仓库是组件，产物（安装包、下载）在产品仓库
[`LocalReel`](https://github.com/LocalReel/LocalReel)。
