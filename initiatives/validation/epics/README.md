# validation — epics (execution order)

1. **decisions** — Rafael's open decisions (1 task, manual)
2. **fountain-input** — PDF → Fountain → parser (2 tasks)
3. **blocking-test** — U2: blocking and cameras from one real scene (1 task, film session)

`fountain-input` waits for decisions 4 and 8. `blocking-test` needs one scene
converted by `fountain-input/1` and nothing else.

Cross-repository: `fountain-input/2` emits `script.harpia` messages, which
start as a `mocap-contracts` task (HANDOFF Q11: Claude defines it when the
need is real).

An epic only merges up into `epics` once all its tasks are `-done` and the suite is green.
