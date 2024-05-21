# Description

This repo only exists to provide a reproducible example for this issue: https://github.com/ipetkov/crane/issues/610

# Bug

`nix flake check` fails with the following error:

```
error: builder for '/nix/store/f99pxdnihgxjyqdayzisn0w1ymzm0swr-cargo-package-deps-0.0.1.drv' failed with exit code 101;
       last 10 log lines:
       >    Compiling dummy v0.1.0 (/build/source/dummy)
       >     Checking quote v1.0.36
       > error: `proc-macro` crate types currently cannot export any items other than functions tagged with `#[proc_macro]`, `#[proc_macro_derive]`, or `#[proc_macro_attribute]`
       >   --> proc_macro/src/lib.rs:14:1
       >    |
       > 14 | pub fn main() {}
       >    | ^^^^^^^^^^^^^
       >
       > error: could not compile `proc_macro` (lib) due to 1 previous error
       > warning: build failed, waiting for other jobs to finish...
       For full logs, run 'nix-store -l /nix/store/f99pxdnihgxjyqdayzisn0w1ymzm0swr-cargo-package-deps-0.0.1.drv'.
error: 1 dependencies of derivation '/nix/store/wi43apknsf5g3j3xga2s49kk36sdnkp7-dummy-0.0.1.drv' failed to build
error: build of '/nix/store/0scs7lmksqm1h67i0pkgccl4y8gwhciv-proc_macro-0.0.1.drv', '/nix/store/wi43apknsf5g3j3xga2s49kk36sdnkp7-dummy-0.0.1.drv' failed
```
