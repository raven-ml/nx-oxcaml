# nx-oxcaml

nx-oxcaml is a high-performance nx backend using oxcaml's unboxed types and SIMD intrinsics.

it belongs to the raven ecosystem (https://github.com/raven-ml/raven) and follows its philosophy and guidelines. it builds against the released `nx` 1.0.0~alpha3 from opam, because raven's development branch needs OCaml 5.5 syntax and oxcaml is based on OCaml 5.4.

## project structure

- `lib/` - main library (`nx_oxcaml` / `nx-oxcaml`), an implementation of the `nx.backend` virtual library
- `test/` - test suite (`test_nx_oxcaml`)
- `bench/` - benchmarks (`bench_nx_oxcaml`)
- `vendor/` - vendored dependencies

## build instructions

the project builds in an opam switch with the oxcaml compiler (`ocaml-variants.5.4.0+ox`); see the README.

```sh
# build
dune build

# run tests
dune test

# run benchmarks
dune exec bench/bench_nx_oxcaml.exe

# watch mode
dune build --watch
```

## important rules

- NEVER stage or commit changes unless explicitly requested
- NEVER run `dune clean`
- NEVER use the `--force` argument
- NEVER try to remove the dune lock file or kill dune when running in watch mode
- NEVER hide warnings and NEVER hide unused variables by adding an underscore
