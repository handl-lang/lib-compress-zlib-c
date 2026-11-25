# lib-compress-zlib-c

`compress-zlib-c` — the zlib backend for the `compress` contract:
raw deflate via `libz`, reached through the C FFI.

## Layout

| path | role |
| --- | --- |
| `src/index.hnl` | the backend module (`compress-zlib-c`) |
| `src/probe.hnl`, `src/probe.test.hnl` | FFI probe + tests |
| `src/compress-zlib-c.test.hnl` | backend tests |
| `pkg.hnl` | manifest — deps `compress`, `libz` (`branch:main`) |
| `scripts/hnl-gate.sh` | `.hnl` gate |
| `workflows/gate.yaml` | CI — shared `handl-gates` campaign |

## Contract

- Implements the `lib-compress` contract over libz's raw deflate —
  distinct from `lib-compress-gzip-c` (gzip `gz*` wrapper format).
- Pure `.hnl` over `ffi.call`; no Rust crate.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
