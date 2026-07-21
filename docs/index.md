---
layout: default
title: PFX Python & HPC
---

# Intro to Python & Supercomputing

Welcome. By the end of this tutorial you will have written real Python code and run it on
**Frontera**, a research supercomputer at the Texas Advanced Computing Center (TACC) in
Austin, Texas.

You do not need to know how to code. You do not need to know what a supercomputer is yet.
You will not use a command line at any point. Everything happens in your web browser.

Set aside about an hour.

## What a supercomputer actually is

A supercomputer is not one giant computer. It's thousands of ordinary computers, called
**nodes**, wired together so they can work on the same problem at the same time.

Frontera has **8,368 nodes**. Each node has **56 processor cores** and **192 GB of memory**,
which adds up to **468,608 cores**, and for this workshop 250 of those nodes are reserved just
for our group.

That's the whole idea behind high-performance computing: if you can split a job into pieces,
many cores can chew through those pieces simultaneously and finish far sooner than one core
working alone. You'll measure that speedup yourself in Part 3.

## What you'll do

1. Get an account on the TACC systems
2. Download a notebook file
3. Start Jupyter on Frontera through a web portal
4. Upload your notebook and run it

Steps 2 through 4 take about five minutes. The rest of the hour is the fun part.

---

## Before you start: get an account

You need a TACC account with access to the CBPC computing resources. **Do this a few days
ahead**, not the morning of, because accounts take time to approve and you'll need to set up
Multi-Factor Authentication.

1. Go to the [CBPC HPC Resources page](https://www.bpccenter.org/current-programs/cbpc-hpc-resources).
2. Click **Request Access** and fill out the form.
3. Watch your email for your TACC account details.
4. Follow the instructions in that email to set up **Multi-Factor Authentication (MFA)**. You
   will not be able to log in without it.

Once you can log into [tap.tacc.utexas.edu](https://tap.tacc.utexas.edu), you're ready.

---

## Step 1 — Download the notebook

A **notebook** is a file that mixes written explanations with code you can run, a piece at a
time. That's what you'll be working in.

Go to the notebook file:

**[intro-to-python-and-hpc.ipynb](https://github.com/ashleyscruse/pfx-hpc/blob/main/notebooks/intro-to-python-and-hpc.ipynb)**

Click the **download icon**, the downward arrow near the top right of the file view. Save
`intro-to-python-and-hpc.ipynb` somewhere you'll remember. Your **Downloads** folder is fine.

**You should now have** a file ending in `.ipynb` on your computer. It may look like a blank
or unfamiliar icon. That's normal, and you don't need to open it here.

> **If it opens as a wall of text instead of downloading:** go back, right-click the download
> button, and choose **Save Link As**. Make sure the saved name still ends in `.ipynb` and not
> `.txt`.

---

## Step 2 — Start Jupyter on Frontera

Right now that notebook is sitting on your laptop. To run it on Frontera, you first need
Frontera to give you a workspace.

You'll use the **TACC Analysis Portal (TAP)**, a website that starts Jupyter for you on a real
Frontera node so you never have to touch a terminal.

Go to **[tap.tacc.utexas.edu](https://tap.tacc.utexas.edu)** and log in with your TACC
username, password, and MFA code.

Now fill out the session form:

| Field | What to choose |
|-------|----------------|
| System | **Frontera** |
| Application | **Jupyter Notebook** |
| Project | **TRA25001** |
| Queue | **normal** |
| Reservation | **Morehouse** |
| Nodes | **1** |
| Time | **2 hours** |

Click **Submit**.

**What's happening:** you just asked Frontera for one of its 8,368 nodes. Your request goes
into a line called a **queue**, and a program called the **scheduler** hands you a node when
one is free. This is how a machine shared by thousands of researchers stays fair.

Wait for the status to change, then click **Connect**. Jupyter opens in your browser.

**You should now see** the Jupyter file browser: a mostly empty list of files, with buttons
along the top.

> **About the reservation.** A reservation sets nodes aside in advance for a specific group, so
> you skip the line entirely. Ours is named **Morehouse** and it's active
> **Tuesday, July 21, 7:00 AM to 1:00 PM (Central)**.
>
> **Working through this on your own later?** The reservation will be gone. Leave the
> Reservation field blank, choose the **development** queue instead of `normal`, and pick
> whichever project you have access to. You may wait a few minutes for a node.

---

## Step 3 — Upload your notebook

Jupyter is running on Frontera, but it can't see your laptop's files yet. Send your notebook over:

1. In the Jupyter file browser, click **Upload** (top right).
2. Pick the `intro-to-python-and-hpc.ipynb` file you downloaded in Step 1.
3. A blue **Upload** button appears next to the file name. Click it to confirm.
4. Click the file name to open it.

**You should now see** the notebook open, starting with a heading that reads
"Intro to Python & Supercomputing on Frontera."

> **Don't see your file after uploading?** Check that you clicked the second blue Upload button.
> Until you do, the file is only staged, not actually uploaded.

---

## Step 4 — Run it

The notebook is a stack of boxes called **cells**. Gray cells hold code. The rest is
explanation, like what you're reading now.

To run a cell: **click it, then press `Shift` + `Enter`.** The cell runs, its output appears
underneath, and you move to the next one.

Work top to bottom. Don't skip cells, because later ones often depend on earlier ones.

The very first code cell prints the name of the machine you're on. When you see something like
`c123-456` appear, that's a real node in a real machine room in Austin, Texas, and you're
using it.

Three things worth knowing:

- **Change things.** Put your own name in, change the numbers, see what happens. That's the point.
- **You cannot break anything.** If a cell throws a red error, read the last line, fix it, and
  run it again. Nothing you type can damage the computer or affect anyone else.
- **Order matters.** If something suddenly stops working, run the cells above it again from the top.

---

## What's inside the notebook

| Part | What you'll do |
|------|----------------|
| 1. Where am I? | Print the machine's name and core count, and confirm you're on Frontera |
| 2. Python basics | Variables, math, text, lists, loops, `if` decisions, and functions |
| 3. Many cores at once | Analyze millions of health records, then model thousands of epidemics, on 1 core vs. all 56 |
| 4. The rest of Frontera | Nodes, storage, software modules, and how jobs get scheduled |
| 5. Wrap-up | A challenge to try on your own |

Part 3 is the one to slow down for. You'll run real jobs the slow way on one core, then across
all 56 cores of your node, and watch the clock. That gap, and the fact that Frontera has 8,368
of these nodes, is the entire reason machines like it exist.

---

## If you get stuck

| Problem | Try this |
|---------|----------|
| Can't log into TAP | Your account may not be approved yet, or MFA isn't set up. Check your TACC email. |
| Session won't start | Confirm the Reservation and Project fields are exactly right. Outside the reservation window, switch to the `development` queue. |
| Notebook won't upload | Confirm the file still ends in `.ipynb`, then click the second blue Upload button. |
| A cell shows a red error | Read the last line of the message. Most errors are typos. Fix and re-run. |
| Everything stopped working | Go to **Kernel → Restart & Clear Output**, then run the cells again from the top. |
| Session disappeared | Your time ran out. Start a new session in TAP and re-upload the notebook. |

---

## Keep going

You just used a national research supercomputer. If you want to keep learning:

- [Frontera user guide](https://docs.tacc.utexas.edu/hpc/frontera/) — the official documentation
- [TACC Analysis Portal](https://tap.tacc.utexas.edu) — where you launched your session
- [Python.org](https://www.python.org) and [W3Schools Python](https://www.w3schools.com/python/) — free practice
