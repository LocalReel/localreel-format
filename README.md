# localreel-format — archived

This crate has been merged into the server workspace as
[`localreel-core/crates/localreel-format`](https://github.com/LocalReel/localreel-core/tree/main/crates/localreel-format).

The backup/artifact schema is a leaf crate with no I/O, but it has no independent
consumer: keeping it in a separate repository only added cross-repo path
dependencies and release coordination. It now shares the core workspace version
and its tests run with `cargo test --workspace`.

This repository is kept read-only for history. Use the core repository for
changes.

## 简体中文

本仓库已归档：crate 已并入服务器仓库
[`localreel-core/crates/localreel-format`](https://github.com/LocalReel/localreel-core/tree/main/crates/localreel-format)。

备份/产物格式是一个无 I/O 的叶子 crate，但没有独立消费者；单独成库只会增加跨仓库
路径依赖与发布协调成本。现在它与 core 共享 workspace 版本，测试随
`cargo test --workspace` 运行。

本仓库只保留只读历史，后续修改请到 core 仓库。
