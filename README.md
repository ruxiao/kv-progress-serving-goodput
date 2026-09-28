# From KV Progress to Serving Goodput

**Mechanism and Admission in Cross-Vendor PD — ICAIS 2026**

Ruxiao Qian · Li Zeng · Dong Liang · Yang LI  
Corresponding author: Yang LI, <liyang@litlit.ai>

[Camera-ready paper](paper_v42_1.pdf) · [Complete code and records, v42_1](https://github.com/ruxiao/kv-progress-serving-goodput/releases/tag/v42_1)

This controlled systems study shows that faster KV-cache write progress can
change request-level service outcomes through prefix admission. In the tested
cross-vendor deployment, strict admission protects short requests at a long-request
latency cost. The whole-request control remains essential: it qualifies 40/40
requests under the primary target.

## Get the full artifact

Open [release v42_1](https://github.com/ruxiao/kv-progress-serving-goodput/releases/tag/v42_1)
and download **heterogeneous_pd_v42_1_reproduction.zip**. Extract it and enter
`heterogeneous_pd_v42_1_reproduction/`.

GitHub's automatic **Source code (zip/tar.gz)** links contain this landing
repository only. The named reproduction attachment contains the complete
experiment code and records. A plain `git clone` does not download those records.

```sh
python3 reproduce.py verify
```

The standard-library verification checks 339 unchanged original files, 18
CPU/loopback checks, and exact reconstruction of five campaign outcome objects.
No GPU, model download, Docker, or experiment-host access is used.

To reconstruct the tables and figures in a separate output directory:

```sh
python3.12 -m venv .venv-records
. .venv-records/bin/activate
python -m pip install -r requirements-records.txt
python reproduce.py rebuild --out reproduction-output
```

The archived validation used Python 3.12.14, Matplotlib 3.9.4 and NumPy 2.3.5;
nine record/table reconstruction commands and seven figure generators passed.
The archive contains dependency instructions, source/data manifests, scientific
plans, exact executed controls, native runtime code, client records, outcomes,
and third-party notices.

## Native replay boundary

The earlier R44/R46 portable launcher has CPU/loopback validation only. Its source
inventory has 32 native qualification applications under the original private
controller; that is not a clean GPU run of the shipped launcher. S14–S18 provide
controls and scientific evidence projections, not complete standalone GPU
launchers. Vendor images, model weights, private deployment files and raw KV
tensors are not included. See `CLEAN_NATIVE_REPLAY_GAPS.md` inside the archive.

No new GPU experiment, workload generalization, sustainable-capacity result,
or uniquely identified CPU/GPU mediator is claimed by this release.

## Integrity and licensing

Reproduction archive SHA-256:

```
e1b5f3c7b71212f39162d18fa083a0c292dd7a9ec2507e18591f21f0bd54ce33
```

Use the release's `heterogeneous_pd_v42_1_SHA256SUMS.txt` to check both the archive
and the paper. The archive has a complete `RELEASE_MANIFEST.json` and the original
scientific `SOURCE_MANIFEST.json`.

The authors' original-code and recorded-data licenses are not yet selected.
Public availability is not an open-source/data license. Existing third-party
MIT/Apache notices are retained. See [LICENSE_STATUS.md](LICENSE_STATUS.md).

Please cite the companion paper; author metadata is in [CITATION.cff](CITATION.cff).
