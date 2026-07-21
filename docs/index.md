---
layout: default
title: PFX Python & HPC
---

# Intro to Python & Supercomputing

A one-hour workshop for the **PFX Pre-Freshman Program**. You will write real Python and run
it on **Frontera**, one of the fastest academic supercomputers in the world, at the Texas
Advanced Computing Center (TACC).

No prior coding or HPC experience required.

**What you'll do today:**
- Prove you're running on a real supercomputer
- Learn the Python you'll use constantly: variables, math, text, lists, loops, decisions, functions
- Make many processor cores work at the same time and measure the speedup
- Meet the core ideas of high-performance computing

---

## Before the workshop: get an account

You need a TACC account with access to the CBPC computing resources.

1. Go to the [CBPC HPC Resources page](https://www.bpccenter.org/current-programs/cbpc-hpc-resources).
2. Click **Request Access** and complete the short form.
3. Watch your email for your TACC account details and set up **Multi-Factor Authentication (MFA)**.

Do this a few days early so your account is ready.

---

## During the workshop: get onto Frontera

Everything happens in your web browser. You will **not** use a command line.

There are three steps: download the notebook, start Jupyter on Frontera, upload the notebook.

### Step 1 — Download the notebook

Go to the notebook file on GitHub:

**[intro-to-python-and-hpc.ipynb](https://github.com/ashleyscruse/pfx-hpc/blob/main/notebooks/intro-to-python-and-hpc.ipynb)**

Click the **download icon** (the downward arrow, top right of the file view) to save
`intro-to-python-and-hpc.ipynb` to your computer. Remember where it saved, usually your
**Downloads** folder.

> If the file opens as a page of text instead of downloading, right-click the download button
> and choose **Save Link As**.

### Step 2 — Start a Jupyter session on Frontera

Go to **[tap.tacc.utexas.edu](https://tap.tacc.utexas.edu)** and log in with your TACC
username, password, and MFA code.

Fill in the session form exactly like this:

| Field | Choose |
|-------|--------|
| System | **Frontera** |
| Application | **Jupyter Notebook** |
| Project | **TRA25001** |
| Queue | **normal** |
| Reservation | **Morehouse** |
| Nodes | **1** |
| Time | **2 hours** |

Click **Submit**. Wait for the job to start, then click **Connect**.

> **Use the reservation.** Our reservation is named **Morehouse** and it is active
> **Tuesday, July 21, 7:00 AM to 1:00 PM (Central)**. It holds nodes aside just for our group, so
> your session starts right away instead of waiting in line. If you forget it, you may wait a long time.

> The notebook that opens is running on a real Frontera compute node. You're on the supercomputer.

### Step 3 — Upload the notebook

You now have Jupyter open in your browser, but it's empty. Put your downloaded file on Frontera:

1. In the Jupyter file browser, click the **Upload** button (top right).
2. Choose the `intro-to-python-and-hpc.ipynb` file you downloaded in Step 1.
3. Click the blue **Upload** button that appears next to the file name to confirm.
4. Click the file name to open it.

### Step 4 — Run it

Click a cell and press **Shift + Enter** to run it. Go top to bottom. Change things, break
things, re-run them. That's how you learn.

---

## Materials

- **[Notebook: Intro to Python & HPC](https://github.com/ashleyscruse/pfx-hpc/blob/main/notebooks/intro-to-python-and-hpc.ipynb)**
- **[Slides (PPTX)](https://github.com/ashleyscruse/pfx-hpc/raw/main/slides/pfx-hpc-slides.pptx)**

## Keep going

- [Frontera user guide](https://docs.tacc.utexas.edu/hpc/frontera/)
- [TACC Analysis Portal](https://tap.tacc.utexas.edu)
- [Python.org](https://www.python.org) &middot; [W3Schools Python](https://www.w3schools.com/python/)
