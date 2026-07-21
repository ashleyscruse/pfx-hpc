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

Everything is browser-based. **No command line.** Short version:

1. Download `notebooks/intro-to-python-and-hpc.ipynb` from this repo.
2. Log into [tap.tacc.utexas.edu](https://tap.tacc.utexas.edu) and start a **Jupyter Notebook**
   session on **Frontera** using the reservation below.
3. **Upload** the downloaded notebook in the Jupyter file browser and open it.

## Reservation

| Field | Value |
|-------|-------|
| Reservation | `Morehouse` |
| Account | `TRA25001` |
| Partition | `normal` |
| Window | 2026-07-21, 07:00-13:00 Central |
| Capacity | 250 nodes / 14,000 cores |

## Notes for facilitators

- TAP launches the notebook inside a Slurm job on a compute node, so the parallel demo
  (`multiprocessing.Pool`) uses the cores that session already holds.
- Students never touch a terminal. The notebook's only shell calls are read-only cells
  (`hostname`, `echo $SCRATCH`, `squeue`) run with `!` from inside Jupyter.
- Job submission (`sbatch`) is not possible from the notebook; it happens from a login node.
  Part 4 shows Slurm commands as vocabulary only, not as something students run.
- Time-test Part 3's prime tasks on the actual node and adjust the workload so the serial run
  lands around 15-20 seconds for a satisfying contrast with the parallel run.
