# Intro to Python & Supercomputing

Welcome. This is a self-guided, one-hour tutorial where you'll write real Python and run it on
**Frontera**, a research supercomputer at the Texas Advanced Computing Center (TACC).

You don't need any coding experience, and you'll never touch a command line. Everything happens
in your web browser.

**Start here: [ashleyscruse.github.io/pfx-hpc](https://ashleyscruse.github.io/pfx-hpc/)**

That page walks you through the whole thing, step by step. The short version is below.

## What you'll learn

- How to write Python: variables, math, text, lists, loops, decisions, and functions
- What a supercomputer actually is: 8,368 nodes, 56 cores each, 468,608 cores in total
- Why using many cores at once matters, by running the same job on 1 core and then on 8 and
  timing both
- How work gets scheduled on a machine shared by thousands of researchers

## The short version

1. **Get an account.** Request access on the
   [CBPC HPC Resources page](https://www.bpccenter.org/current-programs/cbpc-hpc-resources) and set
   up Multi-Factor Authentication. Do this a few days early.
2. **Download the notebook:** [`notebooks/intro-to-python-and-hpc.ipynb`](notebooks/intro-to-python-and-hpc.ipynb).
   Click the download icon on that page.
3. **Start Jupyter.** Log into [tap.tacc.utexas.edu](https://tap.tacc.utexas.edu) and launch a
   **Jupyter Notebook** session on **Frontera**.
4. **Upload and run.** Click **Upload** in the Jupyter file browser, choose your downloaded
   file, open it, and press `Shift` + `Enter` to run each cell.

If any step is unclear, the [full tutorial](https://ashleyscruse.github.io/pfx-hpc/) explains
what to expect at each point and what to do when something goes wrong.

## Doing this during the PFX workshop?

Use these settings when you start your session, so you skip the queue:

| Field | Value |
|-------|-------|
| Project | `TRA25001` |
| Queue | `normal` |
| Reservation | `Morehouse` |

The reservation is active **Tuesday, July 21, 7:00 AM to 1:00 PM Central**.

**Doing this on your own afterward?** Leave Reservation blank, use the `development` queue, and
pick whichever project you have access to.

## What's in this repo

- `notebooks/intro-to-python-and-hpc.ipynb` — the tutorial notebook you'll run
- `slides/pfx-hpc-slides.pptx` — the opening slides
- `docs/` — the tutorial website

---

<details>
<summary>Notes for instructors</summary>

- TAP launches the notebook inside a Slurm job on a compute node, so the Part 3 demo
  (`multiprocessing.Pool`) uses the cores that session already holds.
- Students never open a terminal. The notebook's only shell calls are read-only cells
  (`hostname`, `echo $SCRATCH`, `squeue`) run with `!` from inside Jupyter.
- `sbatch` submission isn't possible from the notebook; it happens from a login node. Part 4
  presents Slurm commands as vocabulary only.
- Time-test Part 3's prime workload on a real node and adjust it so the serial run lands around
  15-20 seconds, which makes the parallel contrast land.
- Suggested hour: ~12 min slides, ~35 min notebook, ~10 min questions.

</details>
