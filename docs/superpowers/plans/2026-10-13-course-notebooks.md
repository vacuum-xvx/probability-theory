# Probability Course Notebooks Implementation Plan

**Goal:** Add the missing required and approved original probability notebooks, validate them from a clean kernel, and publish them to `main`.

**Architecture:** Keep one directory per required homework and a separate `topics/` directory for original thematic notebooks. Each notebook is self-contained, deterministic, and combines a mathematical derivation with executable Python and a concise conclusion.

**Tech Stack:** Python 3, Jupyter Notebook, NumPy, SciPy, Matplotlib, nbformat, nbclient

**Spec:** `docs/superpowers/specs/2026-10-13-course-notebooks-design.md`

## Global constraints

- Preserve `hw1/`, `hw2/`, and `example/` byte-for-byte.
- Use original AI-themed scenarios for topics 2, 4, and 5.
- Seed every stochastic experiment with `numpy.random.default_rng(42)`.
- Execute every new notebook before publishing.

### Task 1: Required homework notebooks

**Files:** Create `hw3/hw3.ipynb` and `hw4/hw4.ipynb`.

- [ ] Add the urn problem with the hypergeometric total-probability formula and Monte Carlo convergence plot.
- [ ] Add tasks 2.9–2.11 with explicit formulas and `scipy.stats` calculations.
- [ ] Validate both files with `nbformat.validate`.

### Task 2: Original thematic notebooks

**Files:** Create `topics/topic2_frequency.ipynb`, `topics/topic4_base_rate_paradox.ipynb`, and `topics/topic5_discrete_distributions.ipynb`.

- [ ] Model a random four-class classifier and visualize convergence to probability `1/4`.
- [ ] Derive Bayes' formula for a fraud detector and verify its posterior probability by simulation.
- [ ] Demonstrate Bernoulli, binomial, and Poisson distributions with AI-system examples, theoretical moments, and plots.
- [ ] Validate all three files with `nbformat.validate`.

### Task 3: Repository navigation and environment

**Files:** Modify `README.md`; create `requirements.txt`.

- [ ] Split README navigation into practical work and thematic notebooks.
- [ ] Link every notebook using a relative path.
- [ ] Pin only lower bounds for `numpy`, `scipy`, `matplotlib`, `jupyter`, `nbclient`, and `nbformat`.
- [ ] Verify all local Markdown links exist.

### Task 4: Execute and publish

- [ ] Execute all five new notebooks using `nbclient.NotebookClient(timeout=180, kernel_name='python3')`.
- [ ] Confirm execution produced no error outputs and revalidate notebook JSON.
- [ ] Confirm no existing notebook changed.
- [ ] Remove implementation-only planning documents from the final tree.
- [ ] Commit the final content and push `main` to `origin`.
