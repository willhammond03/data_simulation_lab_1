# Data Simulation Lab 1: distributions

First data simulation lab for **PSYC 201A** (UC San Diego). You will simulate
the kinds of data psychology experiments produce, and summarize and plot it with
the tidyverse. When you are done you will have:

- Simulated data from normal, binomial, and lognormal distributions
- Built a small simulated experiment with conditions, blocks, and participants
- Summarized and reshaped it with `group_by()`, `summarise()`, and `pivot_longer()` / `pivot_wider()`
- Plotted it with ggplot
- Written sentences whose numbers come from your code (inline R), not by hand

> **Before you start:** finish
> [getting-started-with-r](https://github.com/psyc-201/getting-started-with-r).
> This lab assumes R, RStudio, GitHub Desktop, and the tidyverse are installed,
> and that you have done one edit → commit → push. It needs nothing else: no
> terminal, no extra packages.

---

## Part 1. Make your own copy

Same steps as in getting-started-with-r:

1. At the top of [this repository's GitHub page](https://github.com/psyc-201/data_simulation_lab_1),
   click the green **Use this template** button, then **Create a new repository**.
2. Owner: **your own account**. Name it `data_simulation_lab_1`, leave it
   **Public**, and click **Create repository**.
3. On *your* copy (the header reads `yourname/data_simulation_lab_1`), click
   **Code** → **Open with GitHub Desktop** → **Clone**.

Step-by-step version:
[github-desktop.md](https://github.com/psyc-201/getting-started-with-r/blob/main/docs/github-desktop.md).

## Part 2. Open the project and pick a version

**Double-click `data_simulation_lab_1.Rproj`** to open RStudio inside the
project.

There are two versions of the lab. They cover the same material. Pick **one**:

| File | Pick it if… |
|---|---|
| `distributions-lab-intermediate.qmd` | You are newer to R. Most code is written; you fill in each `___`. |
| `distributions-lab.qmd` | You have used the tidyverse before. You get worked examples and hints, and you write the code. |

`distributions-lab-solutions.qmd` has a complete answer key. Use it to check
your work *after* you have tried a section, not instead of trying.

## Part 3. Work through the lab

Put your name in the `author:` line, then go section by section. Run one chunk
at a time with the green arrow at its top right, and click **Render** to see the
whole document.

| Section | Distribution | Simulates |
|---|---|---|
| A | Normal (`rnorm`) | a continuous measure; worked example |
| B | Binomial (`rbinom`) | trial accuracy (correct/incorrect), then two conditions × four blocks |
| C | Shifted lognormal (`rlnorm`) | reaction times, which are right-skewed |
| D | Shifted lognormal, two conditions | a Posner cueing task: valid vs. invalid cues; bonus: 20 simulated participants |

Two things that make the document behave:

- **`set.seed(2025)`** at the top means the "random" numbers are the same on
  every render, so the numbers in your sentences stay put. Change the seed and
  everything changes.
- **Inline R.** Write `` `r round(mean(norm_df$sim_values), 2)` `` in your text
  and Render replaces it with the number. Sections A and B each ask you to
  write a sentence this way.

In the intermediate version, `error: true` is set at the top, so the document
**renders even while it still has `___` blanks**. The unfinished chunks show an
error in red. When nothing is red, you are done.

## Part 4. Commit, push, and submit

Commit as you go. After each section is a good rhythm. When you are finished:

1. Render one last time and check the HTML looks right.
2. In GitHub Desktop, commit with a message like `Finish simulation lab`, then
   **Push origin**.
3. Submit the link to your repository however your instructor asks.

The rendered `.html` files are ignored by git (see `.gitignore`), so only your
`.qmd` is pushed. If your instructor wants the HTML committed too, delete the
matching lines from `.gitignore`.

## What is in this repository

```
data_simulation_lab_1/
├── data_simulation_lab_1.Rproj          open this to start work
├── distributions-lab-intermediate.qmd   scaffolded version: fill in the ___
├── distributions-lab.qmd                hints-only version
└── distributions-lab-solutions.qmd      answer key
```

There is no `data/` folder: you make all the data yourself.

## Stuck?

1. **Setup errors** (package not found, RStudio not in the project): see
   [troubleshooting.md](https://github.com/psyc-201/getting-started-with-r/blob/main/docs/troubleshooting.md)
   in the getting-started repository.
2. **`could not find function "..."`:** you have not run the `setup` chunk
   (the one with `library(tidyverse)`) since you opened RStudio. Run it, then
   try again.
3. **`object '...' not found`:** a chunk further up has not been run, or
   failed. Run the chunks in order from the top. **Run All Chunks Above**
   (the grey down-arrow next to the green one) does this for you.
4. **Your numbers do not match the solutions exactly:** that is fine as long as
   the parameters match. The solutions file sets the same seed, but if you run
   chunks in a different order or more than once, you draw different random
   numbers. Render from scratch to get the seeded values.
5. Still stuck? Post the **exact** error message in the course forum.

## Resources

- [R for Data Science (2e)](https://r4ds.hadley.nz/): the tidyverse, chapter by chapter
- [Experimentology](https://experimentology.io/): the course textbook
- [Quarto: using R](https://quarto.org/docs/computations/r.html)
