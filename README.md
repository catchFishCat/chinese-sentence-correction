# chinese-sentence-correction

`chinese-sentence-correction` is a Chinese sentence-correction skill for ill-formed sentence rewriting (病句修改), following a minimal-edit and meaning-preserving policy.

## What this skill does

- Corrects common Chinese sentence issues: wording, grammar, word order, redundancy, coherence, and reference clarity.
- Uses a four-step workflow: read intent -> locate errors -> minimal correction -> recheck.
- Outputs only the corrected sentence.

## Skill file

- `SKILL.md`

## Measured results (from real runs)

This repository documents measured results from completed experiments in this workspace.

### A) `no-skill` vs `chinese-sentence-correction` (MuCGEC dev random 1000)

Source report: `experiment/results/experiment_report_mucgec1000_skill_vs_noskill.md`

| Condition | Accuracy | Precision | Recall | F1 | TP | FP | FN | TN |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| `no-skill` | 0.9150 | 0.9109 | 0.9119 | 0.9114 | 869 | 85 | 84 | 44 |
| `chinese-sentence-correction` | 0.9850 | 0.9843 | 0.9843 | 0.9843 | 939 | 15 | 15 | 45 |

- Accuracy delta (`chinese-sentence-correction - no-skill`): **+0.0700**

### B) `third-party-pycorrector-chinese-gec` vs `chinese-sentence-correction` (MuCGEC100)

Source report: `experiment/results/experiment_report_mucgec100_skill_compare.md`

| Condition | Accuracy | Precision | Recall | F1 | TP | FP | FN | TN |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| `third-party-pycorrector-chinese-gec` | 0.9100 | 0.9158 | 0.9062 | 0.9110 | 87 | 8 | 9 | 4 |
| `chinese-sentence-correction` | 0.9900 | 0.9896 | 0.9896 | 0.9896 | 95 | 1 | 1 | 4 |

- Accuracy delta (`chinese-sentence-correction - third-party-pycorrector-chinese-gec`): **+0.0800**

## Important comparability note

- The `no-skill` comparison and the `pycorrector` comparison come from two completed experiments with different sample sizes (1000 vs 100).
- So both are real measured results, but `no-skill` vs `third-party-pycorrector-chinese-gec` should be treated as indirect reference unless run in the same exact setup.

## License

MIT. See `LICENSE`.
