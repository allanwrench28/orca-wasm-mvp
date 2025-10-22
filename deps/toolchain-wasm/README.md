# WASM Math Toolchain

This helper builds GMP, MPFR, and CGAL with the Emscripten toolchain. These
artifacts live under `deps/toolchain-wasm/install` and are picked up by the
CMake glue in `wasm/CMakeLists.txt` and the custom `Find*.cmake` shims.

## Usage

```bash
# From the repo root
bash deps/toolchain-wasm/build_math.sh
```

The script expects Emscripten (via `emcc`) to be in the environment. It will use
`wasm/toolchain/emsdk.env` if present, falling back to a globally available
`emsdk_env.sh`.

Boost must already be staged via `deps/boost-wasm/build_boost.sh`, since CGAL's
headers and libraries are linked against that bundle.

Generated directories (`build`, `downloads`, `src`, `install`) are already
ignored via `.gitignore`.
