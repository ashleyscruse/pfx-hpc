# PFX Python & HPC

A one-hour introduction to Python and supercomputing for the **PFX Pre-Freshman Program**.
Students write Python and run it on **Frontera** at TACC via the **TACC Analysis Portal (TAP)**.

No prior coding or HPC experience required.

## Contents

| Path | What it is |
|------|-----------|
| `notebooks/intro-to-python-and-hpc.ipynb` | The hands-on notebook students run on Frontera |
| `slides/pfx-hpc-slides.pptx` | ~10 opening slides (Morehouse brand) |
| `docs/` | The workshop website (GitHub Pages) with setup instructions |

## The hour

1. **Slides (~12 min)** set the stage: what Frontera is, what it's used for, and why it matters.
2. **Notebook (~35 min)**: Python basics, then a live parallel-computing demo that measures the
   speedup from using many cores at once.
3. **Q&A (~10 min).**

## For students

Setup instructions live on the workshop site: **https://ashleyscruse.github.io/pfx-hpc/**

Short version: request a CBPC account, log into [tap.tacc.utexas.edu](https://tap.tacc.utexas.edu),
start a **Jupyter Notebook** session on **Frontera**, then in a Jupyter terminal run:

```bash
git clone https://github.com/ashleyscruse/pfx-hpc.git
```

and open `pfx-hpc/notebooks/intro-to-python-and-hpc.ipynb`.

## Notes for facilitators

- TAP launches the notebook inside a Slurm job on a compute node, so the parallel demo
  (`multiprocessing.Pool`) uses the cores that session already holds. Request enough cores.
- Job submission (`sbatch`) is not done from the notebook; it happens from a login-node
  terminal. The notebook only runs read-only Slurm commands (`squeue`).
- Time-test Part 3's prime tasks on the actual node and adjust the workload so the serial run
  lands around 15-20 seconds for a satisfying contrast with the parallel run.
