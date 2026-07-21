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
- Why using many cores at once matters, by analyzing millions of health records and modeling
  thousands of epidemics on 1 core and then on all 56, and timing both
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
| Nodes | `3` |
| Tasks | `3` |

The reservation is active **Tuesday, July 21, 7:00 AM to 1:00 PM Central**. The `normal` queue
has a 3-node, 3-task minimum, so request 3 even though the notebook only uses one node.

**Doing this on your own afterward?** Leave Reservation blank, use the `development` queue, and
pick whichever project you have access to.

## What's in this repo

- `notebooks/intro-to-python-and-hpc.ipynb` — the tutorial notebook you'll run
- `slides/pfx-hpc-slides.pptx` — the opening slides
- `docs/` — the tutorial website

---

<details>
<summary>Notes for instructors</summary>

- Requires `numpy` and `matplotlib` in the TAP Jupyter kernel (both are in TACC's `python3`).
  Verify before the session; the risk-by-age bar chart and the epidemic heatmap need matplotlib.
- Part 3 runs each job on 1 core, then on `os.cpu_count()` (56 on a Frontera node), via
  `multiprocessing.Pool` with the `fork` start method so cell-defined functions parallelize.
  This is single-node; it does not span the reserved nodes (that would need MPI/Dask + a batch job).
- Two tunable slots control the serial runtime: `NUM_BATCHES` (default 400 => 20M records) and
  `GRID` (default 400 => 160,000 scenarios). On a real node, size them so the 1-core run is
  ~10-15 s: felt, but not dead air. Frontera's single core is slower than a modern laptop's, so
  start there and adjust.
- Both examples are public health: analyzing a large patient dataset (data) and an epidemic
  parameter sweep (modeling), matching the agenda title "Unlocking What's Possible Through Data
  and HPC." Every timing comparison is 1-vs-many cores on Frontera itself, so the numbers stay
  honest even against a high-end laptop.
- Students never open a terminal. The notebook's only shell calls are read-only cells
  (`hostname`, `echo $SCRATCH`, `squeue`) run with `!` from inside Jupyter.
- `sbatch` submission isn't possible from the notebook; it happens from a login node. Part 4
  presents Slurm commands as vocabulary only.
- Suggested hour: ~10 min slides, ~40 min notebook, ~10 min questions.

</details>
