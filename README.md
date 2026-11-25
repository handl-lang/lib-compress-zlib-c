# lib-compress-zlib-c

`zlib` backend for the `compress` contract (raw deflate via `libz`).

## Layout

```text
src/                     the .hnl sources
pkg.hnl                  package manifest (deps on compress, libz)
scripts/hnl-gate.sh      the gate
workflows/gate.yaml                    bupha entry (handl-gates)
```

## Gate

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.
