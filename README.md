# RUST驱动开发教程

## 单元测试

### 测试工具

- [qemu](https://www.qemu.org/) - 一个开源的虚拟机，可以模拟多种硬件平台。
- [cargo test](https://doc.rust-lang.org/cargo/commands/cargo-test.html)
- [bare-test](https://crates.io/crates/bare-test)

`bare-test` 是一个轻量级的测试框架，专为裸机环境设计。它允许在没有操作系统支持的情况下运行测试(本身是一个小型操作系统)。

### 项目搭建

[https://github.com/drivercraft/bare-test-template](https://github.com/drivercraft/bare-test-template)

点击 "Use this template" 按钮，创建一个新的仓库。

修改 `Cargo.toml` 文件:

```toml
[package]
edition = "2024"
name = "project-name"
version = "0.1.0"
```

`project-name` 替换为你的项目名称。

`src/lib.rs` 中构建你的驱动程序

`tests/test.rs` 中编写测试代码。

### 运行测试

安装 `ostool`

```bash
cargo install ostool
```

运行测试

```bash
cargo test --package project-name --test test -- tests --show-output
# 带uboot的开发板测试
cargo test --package project-name --test test -- tests --show-output --uboot 
```
