# Zig Wasm plugin example

![minimum Zig version](https://img.shields.io/badge/dynamic/regex?url=https%3A%2F%2Fraw.githubusercontent.com%2Ftypst-community%2Fwasm-minimal-protocol%2Frefs%2Fheads%2Fmain%2Fexamples%2Fhello_zig%2Fbuild.zig.zon&search=%5C.%5Cs*minimum_zig_version%5Cs*%3D%5Cs*%22(%5B%5E%22%5D%2B)&replace=%241&logo=zig&label=minimum%20Zig%20version&labelColor=white)

This is a bare-bones Typst plugin, written in [Zig](https://ziglang.org/).

## Compile

To compile this example, you need to first [install the minimum required Zig version](https://ziglang.org/learn/getting-started/).

> [!Important]
> This example may not build using other versions of Zig, as it introduces breaking changes in every release. You can grab the Zig release binaries from the Zig [Download](https://ziglang.org/download/) page.

Then, build this package with:

```sh
zig build -p . -Doptimize=ReleaseSmall
```

## Compile with WASI

If you want to build with WASI, use the `wasm32-wasi` target:

```sh
zig build -p . -Dtarget=wasm32-wasi -Doptimize=ReleaseSmall
```

Then, stub the Wasm binary with:

```sh
wasi-stub hello.wasm -o hello.wasm
```

## Build with Typst

Simply run `typst compile hello.typ`, and observe that it works!

## Further tip: High-level wrappers

[Wasm plugin development — Best of Typst (TCDM)](https://ydx-2147483647.github.io/best-of-typst/#wasm) lists a few Zig wrappers made by the community, namely:

- [typst-community/wasm-zig-typst](https://github.com/typst-community/wasm-zig-typst)

  ![GitHub last commit](https://img.shields.io/github/last-commit/typst-community/wasm-zig-typst)
  ![GitHub Repo stars](https://img.shields.io/github/stars/typst-community/wasm-zig-typst?style=flat)

- [peterhellberg/typ](https://github.com/peterhellberg/typ)

  ![GitHub last commit](https://img.shields.io/github/last-commit/peterhellberg/typ)
  ![GitHub Repo stars](https://img.shields.io/github/stars/peterhellberg/typ?style=flat)
