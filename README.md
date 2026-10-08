# Glossary for Data Science

**800 plain-language definitions for people entering data science and data engineering — no prior knowledge assumed.**

[![Terms](https://img.shields.io/badge/terms-800-blue)](#whats-inside)
[![Categories](https://img.shields.io/badge/categories-23-green)](#the-23-categories)
[![Version](https://img.shields.io/badge/version-2.0-orange)](Glossary-for-Data-Science-v2.0.md)
[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-lightgrey)](LICENSE)

**[→ Read the glossary](Glossary-for-Data-Science-v2.0.md)**

---

## Why this exists

Every data science course, tutorial and job posting assumes you already speak the language. You are three minutes into a video and someone says *"just spin up a lakehouse, register the artifact, and watch for drift"* — and you are still on the first word.

So I wrote the dictionary I wanted on day one.

This started as my own notes while working through a 12-course data science professional certificate, and it grew into something worth sharing: **one file, alphabetical, 800 terms, every definition written for someone who has never seen the word before.** Not a link dump. Not a list of acronyms expanded into other acronyms. Each entry says *what the thing is*, and where it matters, *what it is for* or **the trap it hides**.

No paywall, no signup, no email capture. One Markdown file you can read, search, download, print or fork.

---

## What's inside

| | |
| --- | ---: |
| Terms | **800** |
| Categories | **23** |
| Words of definition | ~38,700 |
| Format | Single Markdown file, A–Z, one entry per concept |
| Prerequisites | **None** |

Each entry follows the same shape — the term, its category in `backticks`, then a short definition:

> ### A/B testing · `Statistics`
>
> A controlled experiment that randomly assigns users or units to a control and a treatment and compares one predefined metric between them. Random assignment is what makes the difference attributable to the change, and everything else — sample size fixed in advance, one primary metric, no peeking — exists to protect that inference.

> ### CUPED · `Statistics`
>
> A variance-reduction technique for online experiments that uses a pre-experiment measurement of each unit as a covariate, then subtracts the part of the outcome that measurement already predicts. Because assignment is random the covariate is balanced across arms, so removing it shrinks the confidence interval without biasing the estimate — often cutting the required sample size by a third or more. It works only if the covariate is measured strictly before the experiment starts; a post-treatment variable reintroduces exactly the bias it was meant to remove.

> ### Amazon S3 · `Cloud Platform`
>
> Object storage organised as buckets of keys, and the default landing zone for raw data on AWS. Durability comes from replication rather than from a file system, so it is cheap and effectively unlimited, but it offers no partial update and no directory semantics — which is why table formats such as Iceberg and Delta exist on top of it.

> ### Zero-shot prompting · `Generative AI`
>
> Asking a model to perform a task with instructions alone and no worked examples, relying on what pretraining already taught it. It is the fastest thing to try and the first to fail on tasks with an unusual output convention.

### What is new in v2.0

v2.0 keeps every v1.1 entry and adds **7 advanced terms** — the methods and systems that start to matter once the fundamentals are in place.

| New term | Category | What it is |
| --- | --- | --- |
| `CUPED` | `Statistics` | Variance reduction in experiments, using pre-experiment data as a covariate |
| `Synthetic control` | `Statistics` | A causal counterfactual built from comparable units when only one was treated |
| `Uplift modelling` | `Machine Learning` | Predicting the change a treatment causes, rather than the outcome |
| `Shapley values` | `Machine Learning` | Principled attribution of one prediction across its input features |
| `Query plan` | `SQL` | What `EXPLAIN` shows, and why a query is slow |
| `Mixture of experts (MoE)` | `Generative AI` | A sparse architecture: many experts, few used per token |
| `LLM-as-judge` | `Generative AI` | Using one model to score another model's output against a rubric |

The first two extend **experiment design and causal inference**, which was the thinnest area of v1.1 — and it is the area these roles interview on hardest. `Query plan` covers the part of SQL that decides whether a query finishes in a second or an hour.

**v1.1, kept in full:** 249 terms across six new categories — `Cloud Platform`, `Data Architecture`, `MLOps`, `Generative AI`, `Analytics & BI` and `Data Governance`.

---

## How to use it

**Jump by letter** — every section is anchored, so a link goes straight to the term:

[0-9](Glossary-for-Data-Science-v2.0.md#0-9) · [A](Glossary-for-Data-Science-v2.0.md#a) · [B](Glossary-for-Data-Science-v2.0.md#b) · [C](Glossary-for-Data-Science-v2.0.md#c) · [D](Glossary-for-Data-Science-v2.0.md#d) · [E](Glossary-for-Data-Science-v2.0.md#e) · [F](Glossary-for-Data-Science-v2.0.md#f) · [G](Glossary-for-Data-Science-v2.0.md#g) · [H](Glossary-for-Data-Science-v2.0.md#h) · [I](Glossary-for-Data-Science-v2.0.md#i) · [J](Glossary-for-Data-Science-v2.0.md#j) · [K](Glossary-for-Data-Science-v2.0.md#k) · [L](Glossary-for-Data-Science-v2.0.md#l) · [M](Glossary-for-Data-Science-v2.0.md#m) · [N](Glossary-for-Data-Science-v2.0.md#n) · [O](Glossary-for-Data-Science-v2.0.md#o) · [P](Glossary-for-Data-Science-v2.0.md#p) · [Q](Glossary-for-Data-Science-v2.0.md#q) · [R](Glossary-for-Data-Science-v2.0.md#r) · [S](Glossary-for-Data-Science-v2.0.md#s) · [T](Glossary-for-Data-Science-v2.0.md#t) · [U](Glossary-for-Data-Science-v2.0.md#u) · [V](Glossary-for-Data-Science-v2.0.md#v) · [W](Glossary-for-Data-Science-v2.0.md#w) · [X](Glossary-for-Data-Science-v2.0.md#x) · [Y](Glossary-for-Data-Science-v2.0.md#y) · [Z](Glossary-for-Data-Science-v2.0.md#z)

**Search for a term** — open the file and use your browser's find (`Ctrl`/`Cmd` + `F`). GitHub renders the whole file, so search hits everything, not just what is on screen.

**Read it as a primer** — it is written to be read top to bottom as well as looked up in a hurry.

**Download it** — clone the repo, or grab the file and open it in Obsidian, VS Code, Typora or any Markdown editor. It is plain text and always will be.

### The 23 categories

| Category | What it covers | Terms |
| --- | --- | ---: |
| `Machine Learning` | Learning algorithms, model practice and evaluation | 96 |
| `Python` | Python language features, data structures and idioms | 78 |
| `Data Engineering` | Pipelines, storage, formats and big-data infrastructure | 73 |
| `Library` | Third-party packages and frameworks (pandas, NumPy, scikit-learn, TensorFlow ...) | 60 |
| `Statistics` | Statistics, probability, experiment design and linear algebra | 58 |
| `Cloud Platform` | Named cloud data and AI platforms and their core services | 47 |
| `Tool` | Applications, platforms and developer tooling | 46 |
| `Data Architecture` | Warehouses, lakes, lakehouses, modelling patterns and pipeline structures | 42 |
| `Generative AI` | Large language models, embeddings, retrieval and prompting | 40 |
| `SQL` | SQL syntax, clauses and query behaviour | 39 |
| `MLOps` | Running models in production: tracking, registries, serving, monitoring | 30 |
| `Methodology` | Process frameworks and lifecycle phases | 26 |
| `Data Governance` | Catalogue, lineage, privacy, ethics and responsible AI | 25 |
| `Analytics & BI` | Business intelligence, metrics and analysis techniques | 23 |
| `Web & APIs` | HTTP, web services, HTML and scraping | 21 |
| `Visualization` | Charts, plotting libraries and visual encoding | 19 |
| `Concept` | General data-science vocabulary | 19 |
| `Database` | Database engines and database concepts | 17 |
| `Cloud` | Cloud computing models and services | 11 |
| `Language` | Programming languages you will meet in data work | 10 |
| `R` | R language features, packages and idioms | 8 |
| `Role` | Jobs and teams in the data world | 6 |
| `Programming` | Language-agnostic programming concepts | 6 |

---

## Who this is for

- **Career changers** who are three weeks into their first data course and drowning in vocabulary.
- **Students and bootcampers** who want one revision file instead of forty browser tabs.
- **Analysts and software engineers** moving sideways into data work.
- **Anyone interviewing** who needs "explain it like I'm five" on a term before they have to explain it like a professional.
- **Non-technical colleagues** — product managers, marketers, recruiters — who sit in data meetings nodding at words nobody has defined.

---

## Scope

The glossary keeps the durable vocabulary of the field — concepts, methods, libraries, platforms, tools, formats, roles and metrics — and leaves out project-specific notes, individual datasets and licence texts. Every definition assumes no background: it says what the term is, and where useful what it is for or the trap it hides.

A few entries are deliberately opinionated. Where a tool has a real limitation, the entry says so. That is the value of a curated glossary over a generated word list.

---

## Repository contents

| File | What it is |
| --- | --- |
| [`Glossary-for-Data-Science-v2.0.md`](Glossary-for-Data-Science-v2.0.md) | **The glossary — 800 terms, A–Z (current)** |
| `README.md` | This page |
| [`LICENSE`](LICENSE) | CC BY 4.0 — share and adapt freely, with attribution |

---

## Contributing

Corrections, sharper wording and missing terms are all welcome.

- **Spotted an error or an unclear definition?** Open an issue with the term name in the title.
- **Want to propose a new term or an edit?** Open a pull request against `Glossary-for-Data-Science-v2.0.md`, keeping the existing format — ``### Term · `Category` `` — followed by a short definition that says what it is and what it is for.
- **Disagree with an entry?** Good — say so in an issue. Definitions get better when someone argues with them.

Please keep the house style: plain language, no prior knowledge assumed, and a concrete trap or use where one exists.

---

## Versioning

| Version | What changed |
| --- | --- |
| **2.0** | +7 advanced terms — `CUPED`, `Synthetic control`, `Uplift modelling`, `Shapley values`, `Query plan`, `Mixture of experts (MoE)`, `LLM-as-judge` |
| **1.1** | +249 terms. Six new categories: `Cloud Platform`, `Data Architecture`, `MLOps`, `Generative AI`, `Analytics & BI`, `Data Governance` |
| **1.0** | First release — the core vocabulary across 17 categories |

Releases ship as their own file, and **the previous file is retired once a new one is current** — there is always exactly one current glossary at the top level. **v1.1 was retired when v2.0 shipped**, so a link to `Glossary-for-Data-Science-v1.1.md` no longer resolves; the current link is [`Glossary-for-Data-Science-v2.0.md`](Glossary-for-Data-Science-v2.0.md).

---

## License

Released under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE). Use it, quote it, translate it, teach with it, put it in your study guide — just credit the source and link back.

---

## Connect

If this saved you some time, a ⭐ helps other people find it. Feedback is welcome on [LinkedIn](https://www.linkedin.com/in/adan-anaya-ds) — tell me which term is missing.
