# SigVTA

SigVTA is an online signature dataset and benchmark for **verification** and **open-set template attribution**. It records genuine signatures under controlled writing conditions together with random and skilled forgeries, and it keeps the link between each skilled forgery and the specific genuine signature the forger was shown.

The full dataset contains 79 target writers and 7,900 signatures. This repository publishes a sample from one writer so that the format can be inspected without an application. The full release is available on request for academic use.

## Repository contents

```text
sample/writer004/
├── NW/   normal writing            20 files
├── SW/   standing writing           20 files
├── HPG/  high pen grip              20 files
├── VSW/  variable-speed writing     20 files
├── RF/   random forgery             12 files
├── SF/   skilled forgery             8 files
└── manifest.json
```

Writer `004` is the public sample. The sample is de-identified: it contains pen trajectories and acquisition metadata only, with no name, contact detail, or identity mapping.

## File format

Each signature is a UTF-8 CSV with seven columns:

| Column | Content | Unit |
| --- | --- | --- |
| 1 | time | ms |
| 2 | X coordinate | mm |
| 3 | Y coordinate | mm |
| 4 | pressure, normalized to [0, 1] | — |
| 5 | derived speed | mm/s |
| 6 | derived direction angle | degrees |
| 7 | pen state: 1 pen-down, 0 pen-up | — |

The nominal sampling interval is 10 ms. `manifest.json` is the index for this sample: it gives each file's label, state, forger, the skilled-forgery reference, row count, duration, and SHA-256.

## Acquisition

Genuine signatures were collected under four controlled conditions (NW, SW, HPG, VSW), in two sessions at least three days apart, ten signatures per condition per session. Forgeries were produced by four forgers who do not overlap with the target writers. A random forgery was written from the target name alone, before the forger had seen any target signature. A skilled forgery was produced while viewing one assigned normal-writing signature, and that assignment is recorded per file.

## Access to the full dataset

The full dataset is not in this repository. It is released only for non-commercial academic research and must not be used for any commercial purpose.

To request it, complete the request form: [ACCESS_REQUEST.md](ACCESS_REQUEST.md), and send the filled form to [Jiang_bohan@163.com](mailto:2846512082@qq.com).

Please include your name, affiliation, and intended use. Recipients agree not to redistribute the data, not to use it commercially, and not to attempt to re-identify participants. Approved requests receive a time-limited download link.

## License

The sample in this repository is released for non-commercial academic research under the terms in [LICENSE](LICENSE). The full dataset is not covered by this file and is supplied separately under its own agreement. Commercial use of either the sample or the full dataset is not permitted.
