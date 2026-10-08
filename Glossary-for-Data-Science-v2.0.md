# Glossary for Data Science

> Version **2.0** · **800 terms** for people entering data science and data engineering — plain-language definitions, one per concept, alphabetical.
>
> New in 2.0: **7 advanced terms** — the methods and systems that come up once the basics are in place.
>
> Each entry shows the term, its category in `backticks`, and a short definition. No prior knowledge assumed.

---

## Contents

#### What is new in 2.0

This version keeps every v1.1 entry and adds **7 advanced terms** — the methods and systems that start to matter once the fundamentals are in place:

| New term | Category | What it is |
| --- | --- | --- |
| `CUPED` | `Statistics` | Variance reduction in experiments, using pre-experiment data as a covariate |
| `Synthetic control` | `Statistics` | A causal counterfactual built from comparable units when only one was treated |
| `Uplift modelling` | `Machine Learning` | Predicting the change a treatment causes, rather than the outcome |
| `Shapley values` | `Machine Learning` | Principled attribution of one prediction across its input features |
| `Query plan` | `SQL` | What `EXPLAIN` shows, and why a query is slow |
| `Mixture of experts (MoE)` | `Generative AI` | A sparse architecture: many experts, few used per token |
| `LLM-as-judge` | `Generative AI` | Using one model to score another model's output against a rubric |

Two of them — `CUPED` and `Synthetic control` — extend experiment design and causal inference, the area where the v1.1 glossary was thinnest. `Query plan` covers the part of SQL that decides whether a query finishes in a second or an hour.

**Kept in full from 1.1:** 249 terms across six categories — `Cloud Platform`, `Data Architecture`, `MLOps`, `Generative AI`, `Analytics & BI` and `Data Governance`.

#### Categories

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

#### Scope

The glossary keeps the durable vocabulary of the field — concepts, methods, libraries, platforms, tools, formats, roles and metrics — and leaves out project-specific notes, individual datasets and licence texts. Every definition assumes no background: it says what the term is, and where useful what it is for or the trap it hides.

Read it straight through as a primer, or jump by letter and by category below.

#### Jump to a letter

[0-9](#0-9) · [A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · [H](#h) · [I](#i) · [J](#j) · [K](#k) · [L](#l) · [M](#m) · [N](#n) · [O](#o) · [P](#p) · [Q](#q) · [R](#r) · [S](#s) · [T](#t) · [U](#u) · [V](#v) · [W](#w) · [X](#x) · [Y](#y) · [Z](#z)

## 0-9

*1 term*

### `__init__` (constructor) · `Python`

A special method known as the constructor that initializes the instance attributes, also called instance variables, when an object is created. It is the only place instance attributes are guaranteed to exist, so forgetting it, or forgetting to pass `self`, produces the `AttributeError` that a class example typically hits. Any setup that must hold for every instance belongs there.

---

## A

*66 terms*

### A/B testing · `Statistics`

A controlled experiment that randomly assigns users or units to a control and a treatment and compares one predefined metric between them. Random assignment is what makes the difference attributable to the change, and everything else — sample size fixed in advance, one primary metric, no peeking — exists to protect that inference.

### Accuracy · `Machine Learning`

The share of predictions that are correct, computed as `(TP + TN) / total`. It is intuitive and misleading on imbalanced data, where predicting the majority class for every row scores high while being useless.

### Ad hoc analysis · `Analytics & BI`

A one-off investigation answering a question nobody had specified in advance, using SQL, a notebook or a BI tool. It is where most genuine insight is found, and it becomes valuable to the organisation only when its result is written back as a governed metric or dataset.

### Aggregate functions · `SQL`

A function such as `SUM`, `MIN`, `MAX`, `AVG` or `COUNT` that takes a collection of like values, typically a whole column, and returns a single value or null. They collapse their input to one value per group, or one value overall when no `GROUP BY` is present. Without them SQL can only list a column, never summarise it.

### AI agent · `Generative AI`

A system in which a language model plans, calls tools, observes results and iterates toward a goal rather than answering in one pass. Its capability comes from the loop and the tools; its risks are compounding errors, unbounded actions and cost that scales with iterations.

### Airbyte · `Data Engineering`

An open-source data-integration platform offering connectors that move data from sources into warehouses and lakes, with a self-hosted or cloud option. Its differentiator is a connector protocol anyone can implement, which is why the catalogue is broad and uneven in quality.

### Algorithmic bias · `Data Governance`

Systematic unfairness in a model's outputs toward a group, usually inherited from biased training data, a proxy variable standing in for a protected attribute, or an objective that encodes historical inequality. It cannot be removed by ignoring protected attributes, because correlated features carry the same signal.

### Aliasing · `Python`

Giving another name to a function or variable, or letting multiple names refer to the same object. The second sense is the consequential one: `B = A` does not copy, so both names point at one list and a mutation through either is visible through both. This is the single most common source of confusing bugs when debugging.

### Altair · `Visualization`

A declarative Python charting library that describes charts as data and emits Vega-Lite specifications, so the plotting code stays compact and the rendered chart becomes an interactive, shareable specification. Interactivity such as tooltips, panning and selection comes from that underlying specification rather than from hand-written callbacks.

### Alteryx · `Cloud Platform`

A self-service analytics tool in which data preparation, blending and modelling are built as a visual workflow of tools rather than as code. It is widely used by analysts who are not programmers, and the workflow itself documents the transformation.

### Amazon Athena · `Cloud Platform`

A serverless query service that runs SQL directly against files in Amazon S3 using a Presto/Trino engine, with no infrastructure to manage and billing per terabyte scanned. Partitioning, columnar formats and compression are what turn a full-table scan into an affordable query.

### Amazon EMR · `Cloud Platform`

AWS's managed cluster service for Apache Hadoop and Apache Spark, letting a job be submitted to a transient cluster that scales and then disappears. Running on spot instances is what makes large batch jobs affordable, at the cost of interruptions.

### Amazon Kinesis · `Cloud Platform`

AWS's managed service for ingesting and processing real-time streams, with Kinesis Data Streams for ordered per-shard delivery and Firehose for delivery straight into S3 or Redshift. Shard count sets the throughput ceiling.

### Amazon Redshift · `Cloud Platform`

AWS's managed, massively parallel columnar data warehouse, organised as a cluster of nodes with a leader that plans queries and compute nodes that run them. Distribution and sort keys decide how evenly the work is spread, and Redshift Spectrum extends queries out to data left in S3.

### Amazon S3 · `Cloud Platform`

Object storage organised as buckets of keys, and the default landing zone for raw data on AWS. Durability comes from replication rather than from a file system, so it is cheap and effectively unlimited, but it offers no partial update and no directory semantics — which is why table formats such as Iceberg and Delta exist on top of it.

### Amazon SageMaker · `Cloud Platform`

AWS's managed platform for the model lifecycle: hosted notebooks, training jobs that provision and release instances, a model registry, feature store, pipelines and endpoints for serving. It removes the infrastructure work around training and deployment while leaving the modelling to you.

### Amazon SageMaker Model Monitor · `Cloud Platform`

An AWS service that captures traffic to a deployed model endpoint, compares it against a training baseline, and raises alerts on drift in data, model quality, bias and feature attribution. Monitoring the input distribution and not only the predictions is what makes silent degradation visible, since ground-truth labels usually arrive late or never.

### Amazon Web Services (AWS) · `Cloud Platform`

The largest cloud provider and the one whose service names dominate data engineering vocabulary: S3 for storage, EC2 for compute, Redshift for warehousing, Glue for ETL, Athena for query and SageMaker for machine learning. Its breadth is the point, and its pricing model is pay-as-you-go.

### Anaconda · `Tool`

A free and open-source distribution for Python and R that bundles the interpreters, a curated scientific stack and the `conda` environment manager. It is the distribution rather than the graphical interface of the same name, and the bundled packaging plus environment tooling is what it is chosen for.

### Analytic Approach · `Methodology`

The process of selecting the appropriate method or path to address a specific data science question or problem. The question fixes the method, rather than the tools already on hand fixing the question, which is what keeps an analysis aligned with the decision it is meant to support.

### Analytical skills · `Concept`

The ability to analyse information systematically, logically and in an organised way. These reasoning skills outlast any particular tool or library, which is why they tend to lead the list of qualities sought in data professionals and why they transfer across every stack.

### Analytics · `Concept`

Examining data to draw conclusions and make informed decisions, and in data science the statistical and data-driven layer of that work. It is commonly staged as descriptive, then diagnostic, then predictive, then prescriptive, each level asking a harder question of the same data.

### Analytics engineering · `Analytics & BI`

The discipline of treating the transformation layer between raw data and business metrics as software: modelled SQL in version control, tested, documented, reviewed and deployed on a schedule. It exists because the logic that defines revenue usually lives in SQL that nobody reviews.

### Analytics Team · `Role`

A group of professionals, including data scientists and analysts, responsible for performing data analysis and modeling. The team structure is what turns individual analyses into a sustained capability, since it carries shared standards for data, methods and the review of results.

### Anomaly detection · `Machine Learning`

An unsupervised task that models the distribution of normal data and scores how far each point deviates from it, so points that do not fit are flagged. Flagged points are candidates for human confirmation rather than proven faults, because a rare but legitimate observation looks identical to an error.

### Anonymisation · `Data Governance`

Removing or altering identifiers so that an individual can no longer be re-identified, which places the data outside personal-data rules if it is genuinely irreversible. It is a high bar: aggregation and stripping names are not enough when other fields still narrow the population.

### Apache Airflow · `Data Engineering`

An open-source platform for programmatically authoring, scheduling and monitoring workflows, originally created by Airbnb. Workflows are written as Python DAGs, which gives dependencies, parallelism and error handling as ordinary code instead of configuration, and makes the schedule reviewable like any other source.

### Apache Beam · `Data Engineering`

A programming model and set of SDKs for defining pipelines that run unchanged in batch or streaming mode, executed by runners such as Dataflow, Flink or Spark. Writing the pipeline once and choosing the engine later is its central idea.

### Apache Cassandra · `Data Engineering`

A highly scalable, distributed wide-column NoSQL database that handles structured and unstructured data across many commodity servers. It offers high availability, fault tolerance and tunable consistency levels, so the write path stays available when nodes fail and the caller decides how much consistency to trade for latency.

### Apache CouchDB · `Data Engineering`

A document-oriented NoSQL database that stores JSON documents, is highly scalable and fault-tolerant, and is the open-source engine beneath IBM Cloudant. Documents are addressed by key and can be replicated between nodes, which suits loosely structured records far better than a fixed relational schema.

### Apache Flink · `Data Engineering`

A distributed stream-processing engine with true event-at-a-time semantics, event-time processing, stateful computation and exactly-once guarantees. It is chosen when streaming logic is complex enough that micro-batching becomes the limitation.

### Apache Hudi · `Data Architecture`

An open table format focused on upserts and incremental consumption, with copy-on-write and merge-on-read table types that trade write amplification against read latency. It is common where records change constantly and downstream jobs must read only what changed.

### Apache Iceberg · `Data Architecture`

An open table format that tracks a table's files in a metadata tree rather than in directory names, giving ACID commits, hidden partitioning, schema evolution and time travel on object storage. Its engine-neutral specification has made it the common interchange layer across warehouses and lakehouses.

### Apache Kafka · `Data Engineering`

A distributed streaming platform for publishing, processing and subscribing to streams of records in real time. Created at LinkedIn, it is built for scalability, fault tolerance and high throughput, and it decouples producers from consumers so each side can run at its own pace.

### Apache NiFi · `Data Engineering`

An open-source data-integration platform with a web-based interface for designing flows between systems, supporting routing, transformation and enrichment. Flows are drawn and configured rather than coded, which shortens the distance between a data movement requirement and a working, observable pipeline.

### Apache PredictionIO · `Tool`

An open-source machine-learning server for building, evaluating and deploying predictive engines such as recommendation, classification and clustering. Its stated limitation is that only Apache Spark ML models can be deployed with it, which constrains the modelling stack behind the server.

### Apache Seldon · `Tool`

An open-source platform for deploying and managing machine-learning models on Kubernetes, supporting nearly every framework, including TensorFlow, Spark ML, R and scikit-learn, and running on Kubernetes and Red Hat OpenShift. Standardising deployment on a cluster is what lets many models be served, versioned and rolled back in one place.

### Apache Spark · `Data Engineering`

A fast, general-purpose cluster-computing engine for large-scale data processing, written in Scala and built around in-memory computation rather than disk-bound MapReduce. Its stack covers Spark SQL, MLlib for machine learning, GraphX for graphs and Spark Streaming, so batch, query, modelling, graph and stream workloads share one engine.

### Apache Spark SQL · `Data Engineering`

A component of the Spark ecosystem providing a programming interface over structured data using SQL, DataFrames and Datasets. Built on ANSI SQL, it scales queries to clusters of thousands of nodes, letting the same declarative query language drive distributed computation.

### Apache Superset · `Tool`

A modern, enterprise-ready open-source business-intelligence web application for visualising and exploring large datasets. It offers charts, tables, maps, geospatial analysis and real-time processing, so exploration and dashboarding happen against the warehouse rather than in a separate desktop tool.

### API key and authorization · `Web & APIs`

An API key is a secure access token or code used to authenticate and authorize access to an API or web service, enabling authenticated requests; authorization means granting permission to perform specific actions or reach particular resources. Most real APIs refuse anonymous traffic, so a request without a valid key fails before any data is returned.

### Application Programming Interface (API) · `Web & APIs`

An interface that allows communication between two pieces of software, defined as a contract of names, inputs, outputs and rules. Because the contract is fixed, the implementation behind it can change or be replaced without breaking callers, which is the property that makes APIs worth designing carefully.

### Area plots · `Visualization`

A plot that displays the magnitude and proportion of multiple variables over a continuous axis, filling the area beneath each line and stacking the series, so the total and each component's share are readable at once. It is a cumulative form of a line plot, also called a stacked line plot.

### Arithmetic Models · `Concept`

A name for the mathematical models used to analyse data and predict outcomes, written `y ≈ f(X; θ) + ε`, where the functional form `f`, the parameters `θ` and the error term `ε` are the model. Choosing and justifying that form and its assumptions is the modelling work.

### Arithmetic Operations · `Concept`

The basic calculations of everyday life such as addition, subtraction, multiplication and division, also called algebraic or mathematical operations. Numeric pitfalls follow from those operations: dividing two integers truncates toward zero in Python 2 but yields a float in Python 3, while division by zero raises `ZeroDivisionError`.

### Array attributes · `Python`

Properties read off an array object that describe it rather than its contents: `dtype` gives the data type of the array elements, `size` and `ndim` give how many elements and how many dimensions it holds, and `shape` gives its dimensions as the number of rows and columns. Checking them before an operation catches most shape and type errors early.

### Artifact · `MLOps`

Any file produced by a run that must be kept: the serialised model, metrics, plots, reports, the preprocessing object. Artifacts are versioned and referenced from the run record, which is what makes a past result inspectable rather than merely reported.

### Artificial Intelligence (AI) · `Machine Learning`

The broad field of machines performing tasks that would require intelligence if a human did them. It is the superset containing machine learning, deep learning and generative AI, so the terms are nested rather than interchangeable, and most everyday commercial AI is machine learning inside that boundary.

### Artificial Neural Networks · `Machine Learning`

Collections of small computing units, called neurons, that process data and learn to make decisions over time. Each unit computes `a = φ(Wx + b)`, a weighted sum passed through an activation function `φ`, and training updates the weights `W` and biases `b` by backpropagated gradients.

### AS (column alias) · `SQL`

The `AS` keyword assigns a name to a result-set column, as in `SELECT COUNT(*) AS conteo`, replacing the engine's expression-derived name for a computed column. Without it an aggregate column is named by its expression text, and every downstream consumer has to quote that; the alias is the public name of a computed column.

### Assignment operator · `Python`

A binary operator that modifies the variable to its left using the value on its right, written `=`. The right-hand side is evaluated first and the result bound to the name, which is why chained and augmented assignments read the way they do, and why `=` is not a test for equality.

### astype() · `Library`

A pandas method that converts the data type of a column or a selected set of columns, as in `df[['a', 'b']] = df[['a', 'b']].astype('float')`. Fixing dtypes is a standard cleaning step, because numeric columns read as strings break arithmetic and quietly inflate memory use.

### Attention mechanism · `Generative AI`

A weighting scheme in which each element of a sequence computes how much it should draw from every other element, using learned query, key and value projections. Self-attention is what lets a model relate a pronoun to the noun it refers to across a long span.

### Attributes · `Python`

The characteristics or properties of an object, accessed using dot notation. They split into class attributes, variables shared among all instances and defined in the class body outside any method, and instance attributes, data specific to each instance and usually initialised inside `__init__`.

### Attribution modelling · `Analytics & BI`

Assigning credit for a conversion across the touchpoints that preceded it — first click, last click, or a data-driven split. Because the assignment rule is a business decision rather than a fact, different models reliably produce different answers about which channel works.

### AUC (area under the ROC curve) · `Machine Learning`

The probability that a randomly chosen positive is scored above a randomly chosen negative, summarising performance across every decision threshold. It is threshold-free, which makes it useful for ranking models, and uninformative about the particular threshold the business will actually use.

### Automation · `Concept`

Using tools and techniques to streamline data collection and preparation processes. Preparation dominates the effort in most projects, so automating the repetitive parts is what frees time for modeling and problem-solving, the work that actually requires judgement.

### AutoML · `MLOps`

Tools that automate part of model development — preprocessing, algorithm and hyperparameter search, sometimes architecture search — and return a ranked set of candidate models. It is fast at producing a competent baseline and poor at producing an explanation, so its output still needs interpretation.

### Avro · `Data Architecture`

A row-oriented binary format that carries its writer schema with the data and supports schema evolution, which makes it a common choice for record-at-a-time streaming and message serialisation rather than for analytical scans.

### AWS DynamoDB · `Database`

Amazon's managed NoSQL database that stores and retrieves data in key-value or document formats such as JSON. The key schema effectively is the query model, so access patterns must be designed up front and full scans are slow and expensive.

### AWS Glue · `Cloud Platform`

AWS's serverless data-integration service: crawlers infer schemas into the Glue Data Catalog, and jobs run Spark-based extract, transform and load without a cluster to manage. It is the standard ETL layer between S3 and Redshift or Athena.

### Azure Blob Storage · `Cloud Platform`

Microsoft's object storage, with the hierarchical-namespace variant (ADLS Gen2) providing directory semantics that analytics engines expect. It is the storage layer under Synapse, Fabric and Azure Databricks.

### Azure Data Factory · `Cloud Platform`

Microsoft's cloud orchestration and ETL service, where pipelines of activities move and transform data between on-premises and cloud stores, with mapping data flows for Spark-based transformation. It is the scheduling backbone under Synapse and Fabric pipelines.

### Azure Event Hubs · `Cloud Platform`

Microsoft's managed event-streaming service, built for high-throughput telemetry ingestion with partitions, consumer groups and retention windows. It is the Azure equivalent of Kafka, with a Kafka-compatible endpoint.

### Azure Machine Learning · `Cloud Platform`

Microsoft's managed environment for training, tracking and deploying models, organised into workspaces with compute clusters, datastores, environments and pipelines. It integrates with Azure DevOps and GitHub for the operational half of the lifecycle.

### Azure Synapse Analytics · `Cloud Platform`

Microsoft's analytics service combining dedicated and serverless SQL pools, Apache Spark pools and data-integration pipelines in one workspace. It is the Azure route for querying a warehouse and a lake with the same SQL surface.

---

## B

*32 terms*

### Backfill · `Data Architecture`

Reprocessing historical periods after a logic change, a bug fix or a new source, so the corrected definition applies to the past as well as the future. A pipeline is only as good as its ability to be re-run over an arbitrary date range.

### Bagging · `Machine Learning`

Training many copies of one model on bootstrap resamples of the data and averaging their predictions, which reduces variance without much changing bias. It is most effective with high-variance, low-bias learners such as deep decision trees.

### Bar charts · `Visualization`

A chart in which the length of each bar represents the magnitude or size of a feature, drawn vertically with `kind='bar'` or horizontally with `kind='barh'`. Vertical bars suit time series, while horizontal bars suit long category labels, so the orientation is a readability decision rather than a stylistic one.

### Baseline model · `Machine Learning`

The simplest defensible predictor — the majority class, the previous period's value, a single-feature linear model — against which any sophisticated model must be compared. Reporting an improvement without a baseline hides whether the problem was hard or the model was merely complicated.

### Batch inference · `MLOps`

Scoring a large set of records in one scheduled job and writing predictions back to a table. It is cheap and simple, and it is the right answer whenever the decision does not need a fresher score than the batch interval.

### Batch processing · `Data Architecture`

Processing data in bounded groups on a schedule — nightly, hourly — where latency is measured in minutes or hours and throughput is the priority. It is simpler and cheaper than streaming, and it remains the right answer for most reporting.

### Bayes' theorem · `Statistics`

`P(A|B) = P(B|A) · P(A) / P(B)`, which expresses the posterior as the likelihood times the prior, normalised by the evidence. It is the formula behind Bayesian analysis and behind the Naive Bayes classifier, and its practical value is that it turns a hard conditional probability into easier ones.

### Bayesian Analysis · `Statistics`

A statistical technique that uses Bayes' theorem to update probabilities as new evidence arrives. The posterior from one round becomes the prior for the next, so evidence accumulates instead of being discarded, and the result is a distribution over parameters rather than a single point estimate.

### BETWEEN · `SQL`

A range predicate equivalent to a pair of comparisons: `WHERE pages BETWEEN 290 AND 300` means the same as `WHERE pages >= 290 AND pages <= 300`, and is inclusive at both ends. With `DATETIME` values, `BETWEEN '2024-01-01' AND '2024-12-31'` silently excludes everything after midnight on the last day, the classic boundary bug, so prefer `>= a AND < b`.

### Bias and variance · `Machine Learning`

Two components of prediction error: bias is how far predictions are systematically off, while variance is how much a model's predictions fluctuate across samples. They trade off against each other as model complexity rises, and techniques such as bagging or bootstrap aggregating reduce variance by averaging many models.

### Big Data · `Data Engineering`

Vast amounts of structured, semi-structured and unstructured data, characterised by the five V's. Its analysis yields competitive advantage and drives digital transformation, and the volume is only meaningful in relation to the tools and time available to process it.

### Big Data Cluster · `Data Engineering`

A distributed computing environment of thousands or tens of thousands of interconnected computers that collectively store and process large datasets. Work is spread across the nodes because no single machine can hold or process the data alone, which is why cluster architecture dominates large-scale storage and compute.

### BigDL · `Library`

A deep-learning library for Spark's Scala API, giving distributed deep learning on the JVM side of the Spark ecosystem. It lets Spark clusters train neural networks without moving data into a separate Python or GPU framework, at the cost of being tied to the Scala and JVM surface.

### Binary Classification Model · `Machine Learning`

A model that classifies data into two categories, such as yes/no or stop/go outcomes. It is the precondition for the ROC curve, the true- and false-positive rates and the discrimination criterion, all of which are defined only for the two-class case.

### Binning · `Machine Learning`

Grouping continuous values together into bins, typically with `bins = np.linspace(df['horsepower'].min(), df['horsepower'].max(), 4)` and `pd.cut(df['horsepower'], bins, labels=['Low','Medium','High'], include_lowest=True)`. It converts a continuous variable into an ordinal one, giving a categorical axis to group by and a hedge against non-linearity, since each bin can take its own level.

### Bitbucket · `Tool`

A web-based Git repository hosting service whose distinguishing features are pull requests, code review and branch permissions. It is one of the common hosted options alongside GitHub and GitLab, and branch permissions are what let a team protect its main line of work.

### Blue-green deployment · `MLOps`

Running two identical production environments so a release is validated on the idle one and then made live by switching traffic, with the previous environment kept for an instant rollback. It trades the cost of duplicated infrastructure for a deployment that does not interrupt service.

### Boolean · `Python`

The two-valued type whose literals are `True` and `False`, also described as algebraic notation representing logical propositions by the binary digits 0 (false) and 1 (true). Every condition, comparison and filter evaluates to one, and `True`/`False` satisfy `type(x) == bool` while also behaving as the integers 1 and 0.

### Boosting · `Machine Learning`

Training models sequentially so each one focuses on the examples the previous ensemble got wrong, producing a low-variance, low-bias learner from weak ones. It is more sensitive than bagging to noisy labels and to hyperparameters such as learning rate and tree count.

### Box plots · `Visualization`

A plot that draws the distribution of a variable as a box with a median line and a box spanning the lower and upper quartiles, with whiskers extending to the furthest points within 1.5 times the interquartile range and points beyond that drawn individually as outliers. This makes skew and outlying values visible in a single compact graphic.

### Branch · `Tool`

A movable pointer to a line of work within a repository. Branches isolate changes so they can be tested before being merged back into the main branch, which is what allows several people to work on the same codebase without overwriting one another.

### Branching (if / elif / else) · `Python`

The process of altering the flow of a program based on conditions, typically using `if`, `elif` and `else` statements. Conditions are tested in order and the first true one selects the block that runs, so ordering the tests correctly is part of the logic rather than a formatting choice.

### break and continue · `Python`

The two loop-control statements: `break` leaves the loop immediately, while `continue` abandons the current iteration and goes on to the next. They distinguish "stop as soon as you know" from "skip this one and keep going", the two most common patterns when searching through a sequence.

### Broad Network Access · `Cloud`

The property of cloud resources being reachable via standard mechanisms and platforms, such as mobile devices, laptops and workstations, over a network. Because access depends on ordinary network protocols rather than special hardware, services are consumed from anywhere the client can connect.

### Broadcasting · `Python`

NumPy's rule that allows arrays of different shapes to be combined in element-wise operations by automatically extending the smaller array to match the shape of the larger one. Multiplying an array by a scalar is the simplest case, where each element is scaled and a new array is returned.

### Browser · `Tool`

A software application that enables users to access and interact with web content, displaying websites and web applications. It is the reference implementation of the client role in web interactions, and it is the tool used to inspect an element on a page before scraping it.

### Browser-Based Application · `Tool`

An application that users access through a web browser, typically on a tablet or other mobile device, providing easy access to a model's insights. It is the most common delivery surface for a deployed model, since it requires no installation by the people who need the predictions.

### Bubble plots · `Visualization`

A variation of the scatter plot that displays three dimensions of data, `x`, `y` and `z`. The data points are replaced with bubbles, and the size of each bubble is determined by the third variable `z`, also known as the weight, so magnitude is encoded by area as well as position.

### Built-in functions · `Python`

Functions always available in Python without an import, such as `len` to find the length of a sequence or `sum` to find the total. `len` takes a sequence or a collection such as a dictionary or set, while `sum` takes an iterable such as a tuple or list, which constrains what each can be called on.

### Business Insights · `Concept`

Insights derived from data that inform a business decision — what customers do, where cost sits, which segment is growing. They are the output the analytical work exists to produce, and their value is judged by the decision they change rather than by their sophistication.

### Business intelligence (BI) · `Analytics & BI`

The practice and tooling of turning stored data into reports, dashboards and self-service exploration that business users act on. It is the consumption end of the data platform: the warehouse models the data, and BI decides how a decision-maker sees it.

### Business Understanding · `Methodology`

The initial phase of the data science methodology: seeking clarification and understanding of the goals, objectives and requirements of a task or problem. Its primary goal is to understand the business problem and determine which data is needed to answer the core business question, before any data work begins.

---

## C

*72 terms*

### C++ · `Language`

A general-purpose language, an extension of C often described as "C with Classes", that improves processing speed, enables system programming and gives broader control. It is the systems layer behind tools such as TensorFlow, MongoDB and Caffe, which trade development convenience for performance and memory control.

### Caffe · `Library`

A deep-learning algorithm repository built in C++ with Python and MATLAB bindings. It belongs to the framework lineage that predates mainstream TensorFlow and PyTorch use, and its C++ core with scripting bindings set the pattern later frameworks followed.

### Callbacks · `Library`

A callback function is a Python function that is automatically called when an input component's property changes, as in a Dash app where the function's return value updates an output component. Declaring inputs, outputs and the function that links them is the whole of the interaction, so reactivity is expressed rather than wired by hand.

### Canary deployment · `MLOps`

Releasing a new model to a small percentage of traffic, watching the metrics that would reveal harm, and widening the share only if they hold. It bounds the blast radius of a bad release to the exposed fraction.

### caret · `R`

An R library for machine learning that provides a unified `train()` interface over many models, with resampling, preprocessing and tuning handled by the same call. It is now largely superseded in idiom by tidymodels, though the interface it established still shapes how R users tune models.

### Case study · `Methodology`

An in-depth analysis of one instance of a chosen subject to draw insight that informs theory, practice or decision-making. Depth into a single case buys context and mechanism that a broad sample cannot give, at the cost of generalising only with care.

### Causal inference · `Statistics`

Estimating what would have happened under a different intervention, rather than describing associations. Its toolkit includes randomised experiments, natural experiments, difference-in-differences, instrumental variables and matching, and its central quantity is always a counterfactual that must be argued for rather than observed.

### Central limit theorem · `Statistics`

The result that the distribution of the sample mean approaches a normal distribution as the sample grows, whatever the shape of the underlying population, provided the observations are independent and the variance is finite. It is the reason normal-based confidence intervals and tests work so broadly, and it says nothing about the distribution of the raw data.

### Ceph · `Data Engineering`

A free, open-source software-defined storage platform for hybrid cloud and modern data centres that unifies object, block and file storage under one scalable system. Presenting S3-like object, VM disk block and NFS-like file access from one cluster means one storage layer can serve very different workloads.

### Chain-of-thought prompting · `Generative AI`

Asking a model to work through intermediate reasoning steps before giving a final answer, which improves results on arithmetic, logic and multi-step problems. The visible reasoning is not a guarantee of correctness, and it should be verified rather than trusted.

### Champion-challenger testing · `MLOps`

Running the deployed model (champion) and a candidate (challenger) side by side on live traffic or on the same holdout, and promoting the challenger only if it wins on the metric that matters. It makes model replacement an evidence-based decision rather than a preference.

### Change data capture (CDC) · `Data Architecture`

Reading a database's write-ahead or binlog stream to emit every insert, update and delete as an event, so downstream systems stay in sync without repeatedly querying the whole table. It turns a batch extraction into an incremental one and preserves deletes, which a periodic full dump cannot.

### CHAR versus VARCHAR · `SQL`

Two character string types: `CHAR` is a fixed length string, while `VARCHAR` is a variable length string that can hold up to a declared maximum, such as 24 characters. A `CHAR(9)` always occupies nine characters and is padded, whereas a `VARCHAR(9)` occupies what is stored plus a length indicator, so the choice affects storage and comparison behaviour.

### Chief Data Officer (CDO) · `Role`

An executive role responsible for data-related initiatives, governance and strategy, ensuring data is central to digital transformation. The role exists because data decisions cross departmental boundaries and need an owner with authority over standards, access and quality rather than only over tooling.

### Chief Information Officer (CIO) · `Role`

The executive responsible for an organisation's information technology and computer systems, contributing the technology aspects of digital transformation. The remit covers the platforms and infrastructure on which data work runs, which is why the boundary between this role and the data-focused executive role is often negotiated rather than fixed.

### Choropleth maps · `Visualization`

A thematic map in which areas are shaded or patterned in proportion to a statistical variable such as population density or per-capita income. It shows how a measurement varies across a geographic area, and how much it varies within one region, and in practice it is drawn by binding a boundary file of country geometry to the data.

### CI/CD · `MLOps`

Continuous integration, where every change is merged and automatically tested, and continuous delivery or deployment, where a passing build is released automatically. For machine learning the pipeline additionally validates data and model quality, since a passing code test says nothing about a model's accuracy.

### Class · `Python`

A blueprint or template for creating objects that defines the structure and behaviour its objects will have, declared with the `class` keyword and conventionally named in CamelCase. The analogy is a cookie cutter and the cookies cut from it, so one class backs many objects that share behaviour but hold their own data.

### Class Imbalance · `Machine Learning`

The unequal proportion of classes in a labelled dataset, which is one of the things worth checking early along with data types, missing values, duplicates and outliers. A heavily skewed target can make accuracy misleading and quietly bias a model toward the majority class, so it is a property of the data to design around.

### Classification · `Machine Learning`

Supervised learning that assigns each observation to one of a fixed set of categories, producing a discrete output rather than a number. Its standard techniques are logistic regression, decision trees, support vector machines, k-nearest neighbours and neural networks, and it is evaluated with a confusion matrix, precision, recall and AUC — with the decision threshold chosen from the relative cost of the two kinds of error.

### CLI · `Tool`

A command line interface, a program driven by typed commands rather than by menus and panes. A prompt reads a line, the shell parses it, a program runs and writes to the same stream, so there are no hidden widgets and no state that cannot be seen; commands such as `git init`, `git add` and `pip install` are CLI invocations.

### ClickHouse · `Database`

A columnar, open-source analytical database built for real-time aggregation over very large event tables, with MergeTree engines that sort and index data at insert time. It answers high-frequency analytical queries in milliseconds, which is why it is common in product analytics and observability.

### Client · `Web & APIs`

The user or code accessing an API, the party that initiates the request. Because the client starts the exchange, it owns the timeout, retry and error-handling logic, which is why resilience is designed into the caller rather than the service.

### Clone · `Tool`

Copying a repository, including its full history, so work can be done locally and synchronised back to the original. Because the entire history travels with the copy, cloning gives a complete offline working environment and full local version history rather than just the current files.

### Cloud Computing · `Cloud`

Delivery of on-demand computing resources, including networks, servers, storage, applications, services and data centres, over the Internet on a pay-for-use basis. Because capacity is provisioned on demand and billed by use, the spending model and the capacity planning model change together.

### Cloud databases · `Database`

Databases delivered as cloud services, such as IBM Db2 on Cloud, PostgreSQL on IBM Cloud, Oracle Database Cloud Service, Microsoft Azure SQL Database and Amazon Relational Database Services. They can run in the cloud either as a virtual machine that the customer manages or as a managed service delivered by the vendor.

### Cloud Deployment Models · `Cloud`

Categories describing where cloud infrastructure resides, who manages it and how resources are made available: public, private and hybrid. The deployment model fixes the ownership and control boundaries around the platform, which is separate from which service model runs on top of it.

### Cloud Service Models · `Cloud`

Models based on the layers of the computing stack, namely IaaS, PaaS and SaaS, representing different cloud offerings. The model fixes the shared-responsibility boundary, so choosing one decides how much patching, scaling and runtime management stays with the customer.

### Cloudant · `Database`

A database-as-a-service offering that is, in the background, based on the open-source Apache CouchDB. It is a clean example of an open-source engine being wrapped as a managed service, where the customer gets the API and operational burden of running it is handled by the provider.

### Clustering · `Machine Learning`

The unsupervised technique of grouping similar points without labels — by minimising within-cluster distance (k-means), by joining the closest groups (hierarchical) or by finding dense regions (density-based, such as DBSCAN). The result depends on feature scaling, the distance metric and the number of clusters, so those choices belong with the results; the clusters describe structure in the data rather than ground truth, and their labels come from interpretation.

### Code Asset Management · `Concept`

The function that stores and manages source code, tracks changes and supports collaborative development. In practice it is version control plus a hosting platform such as GitHub, GitLab or Bitbucket, with code review and continuous integration and delivery on top, so that changes are proposed, reviewed and tested in a consistent way.

### CodePen · `Tool`

A social development environment that runs code in the browser. It is used to host and share in-browser model demos, letting a pretrained model be tried by anyone with a link and no installation, which removes the setup step from evaluating a model.

### Cohort · `Statistics`

A group of individuals who share a common characteristic or experience and are studied or analysed as a unit. Defining the cohort turns a broad question into a row-level dataset with a known denominator, which is what makes comparison between groups meaningful.

### Cohort analysis · `Analytics & BI`

Grouping users by a shared starting event, such as the month of first purchase, and tracking each group over time to compare behaviour. It separates genuine product change from growth-driven aggregate movement, which a single blended average hides.

### Collinearity · `Machine Learning`

Strong correlation between features, which makes their individual contribution to a model hard to separate. The standard check is to analyse a correlation matrix of pairwise correlations and eliminate strong dependencies by keeping the best feature from each correlated group, for instance retaining `ENGINESIZE` over `CYLINDERS` because it correlates more strongly with the target.

### Columnar storage · `Data Architecture`

Storing each column's values contiguously instead of storing rows, so an analytical query reads only the columns it names and compresses extremely well because values in a column share a type and often repeat. It is the reason warehouse queries over billions of rows return in seconds.

### ColumnTransformer · `Machine Learning`

A scikit-learn estimator that applies different transformations to different column subsets and concatenates the results into a single feature space ready for a model. It matters because numeric and categorical columns usually need separate preprocessing paths, which earlier whole-frame approaches forced into one inappropriate path.

### Comments · `Python`

Lines of text that are ignored by the Python interpreter when executing the code, written starting with `#`, as in `# This is a comment`. They are the only durable record of intent inside a script or notebook, and labelling each example with what it demonstrates keeps that intent legible later.

### Commit · `Tool`

A recorded snapshot of the staged changes, carrying a message, author, time and parent commit. It is the immutable unit of history from which branches, merges and reverts are built, so the discipline of small, well-described commits is what makes history usable.

### Commodity Hardware · `Data Engineering`

Standard off-the-shelf hardware components used in a big-data cluster, giving cost-effective storage and processing without specialised hardware. Building clusters from ordinary machines is what makes distributed storage and computation affordable at scale, and it is why replication and fault tolerance in software matter more than exotic hardware.

### Comparison operators · `Python`

Operators used to compare values and return Boolean results, namely `==` (equal), `!=` (not equal), `<`, `>`, `<=` and `>=`. They work on integers, strings and floats, and confusing `==` with the single `=` is the most common beginner error, since one compares two values and the other rebinds a name.

### Composite primary key · `SQL`

A primary key declared over more than one column, as in `PRIMARY KEY (LOCATION_ID, DEPT_ID)`, so uniqueness is enforced across the combination rather than on any single column. It is the standard relational answer to a many-to-many relationship: the junction table's identity is the pair, so each part alone may repeat while the pair must not.

### Computational notebook · `Tool`

Open-source document format that fuses executable code, its computational output, explanatory prose and multimedia resources into a single shareable artefact; Jupyter Notebook is the popular instance and supports dozens of languages, so analysis, evidence and narrative stay interleaved instead of scattered.

### Computational thinking · `Concept`

Problem-solving approach that breaks a large problem into smaller parts and applies algorithms, logic and abstraction to build solutions, through four activities: decomposition, pattern recognition, abstraction and algorithm design, the mental toolkit that precedes any code being written.

### Concatenate · `Python`

Joining values together end to end in a chain, and on strings the operator is `+`, as in `concatenated_string = string1 + string2`. Both operands must be strings, so mixing a string with a number raises `TypeError` until the number is converted with `str()` first.

### Concept drift · `MLOps`

A change in the relationship between inputs and target, so the same features now imply a different outcome. It cannot be detected from inputs alone and requires labels or a proxy, which is why delayed ground truth is the central operational problem in monitoring.

### Conceptual Model · `Methodology`

A simplified representation of a real-world system, built to analyse that system or predict its behaviour rather than to describe its machinery. It is the sense of model that is neither code nor algorithm: an abstraction of the domain that a formula or a program may later implement.

### Conditions · `Python`

Expressions that make decisions in code, executing specific blocks only when a given expression evaluates to `True` or `False`; a condition is the sole thing an `if` statement accepts. Every filter, validation and guard reduces to one, and a truthy non-Boolean value can silently decide the branch.

### Confidence interval · `Statistics`

A range computed from the sample that, under repeated sampling, would contain the true value a stated proportion of the time — 95 % being conventional. Reporting it beside a point estimate shows how much precision the data actually supports, and a wide interval is an honest answer.

### Confounding variable · `Statistics`

A variable that influences both the treatment and the outcome, creating an association that is real in the data but not causal. Randomisation removes it by design; observational studies can only adjust for the confounders they measured, which is why unmeasured confounding is the standing objection to causal claims from such data.

### Confusion matrix · `Machine Learning`

The four-cell table of true positives, false positives, true negatives and false negatives that every binary classification metric is computed from. Reading it is the fastest way to see which kind of error a model makes, which matters more than the single accuracy number it also yields.

### ConfusionMatrixDisplay · `Machine Learning`

Scikit-learn's native confusion-matrix visualiser: it annotates the counts in each cell, labels the axes from the matrix shape or from `display_labels=`, and needs no pandas, unlike the hand-built seaborn `heatmap` alternative that requires a `DataFrame` of counts, `annot=True`, `fmt='d'` and manual axis labels.

### Connection object · `SQL`

One of the DB API's two core concepts, representing a session with a database and managing its transactions. Its methods are `.cursor()`, returning a new cursor over that connection, `.commit()`, writing pending changes to the database, `.rollback()`, undoing back to the start of the pending transaction, and `.close()`, releasing the connection.

### Container · `MLOps`

An isolated, lightweight runtime built from an image, sharing the host operating system kernel while carrying its own file system, libraries and processes. Containers give reproducibility and isolation at far lower cost than a virtual machine, which is why model serving and pipelines are usually containerised.

### Context manager (with) · `Python`

The `with` statement used to open and process a file attribute, guaranteeing the resource is released when the block ends, normally or by exception. It is the `finally` guarantee applied to files, so a crash mid-read still closes the handle rather than leaking an open descriptor.

### Context window · `Generative AI`

The maximum number of tokens a model can consider at once, covering the system prompt, conversation history, retrieved documents and the answer. Everything outside it is invisible to the model, and cost and latency grow with what fills it.

### Continuous training · `MLOps`

Automatically retraining and revalidating a model on a schedule or on a trigger such as detected drift, then promoting the new version if it passes the gates. It turns retraining from an occasional project into a pipeline with a defined promotion rule.

### Control group · `Statistics`

The comparison group that receives no treatment, a placebo or the current standard, providing the counterfactual against which the treatment group is measured. Without it, any change over time is attributable to the treatment, including the change that would have happened anyway.

### Copilot · `Generative AI`

An assistant embedded in a working environment — an IDE, a spreadsheet, a chat client — that generates suggestions in the context of what the user is doing. Convenience comes from the integration, and review of its output remains the user's responsibility.

### Correlation is not causation · `Statistics`

The principle that a statistical association between two variables does not establish that one causes the other, since a hidden confounder or reverse direction can produce the same coefficient. In worked `Curb-Weight vs. Price` data the correlation is `0.83441`, a strong relationship that still licenses no causal claim.

### COUNT(*) versus COUNT(column) · `SQL`

Two aggregate forms with different meanings: `COUNT(*)` is a row count that takes no column argument, while `COUNT(expr)` increments only where the expression is not `NULL`. They agree on complete data and diverge exactly where the column has missing values, the first place a beginner's row count goes wrong.

### CREATE TABLE and DROP TABLE · `SQL`

`CREATE TABLE table_name ( column1 datatype constraints, column2 datatype constraints, ... );` defines a table's columns, types and constraints, while `DROP TABLE COUNTRY;` removes the table and its rows entirely. Because the drop discards the schema, the usual recipe drops the name before recreating it.

### CRISP-DM · `Methodology`

Cross-Industry Standard Process for Data Mining, a widely used methodology with six phases: business understanding, data understanding, data preparation, modelling, evaluation and deployment. The phases are checkpoints rather than a straight line — evaluation routinely sends a project back to earlier framing — which is why it is described as cyclical.

### cross_val_score() · `Machine Learning`

Scikit-learn's k-fold cross-validation helper: `cross_val_score(lre, x_data[['attribute_1']], y_data, cv=n)` partitions the data into `n` folds and returns one score per fold, whose `Rcross.mean()` and `Rcross.std()` report performance and its spread. A single split yields one number from one arbitrary partition; the fold spread is the honest report.

### CRUD · `Database`

The four operations performed on rows of an existing table: Create, Read, Update and Delete. Data Manipulation Language statements provide them, so CRUD names the row-level job while DDL names the structural job of defining and removing the tables themselves.

### CSV · `Data Engineering`

Comma-Separated Values, a plain text file format storing tabular data where each line is a row and commas separate the values of different columns. It assumes a line per record, a comma delimiter and no enforced types; `.txt` holds plain text without any prescribed structure at all.

### CUPED · `Statistics`

A variance-reduction technique for online experiments that uses a pre-experiment measurement of each unit as a covariate, then subtracts the part of the outcome that measurement already predicts. Because assignment is random the covariate is balanced across arms, so removing it shrinks the confidence interval without biasing the estimate — often cutting the required sample size by a third or more. It works only if the covariate is measured strictly before the experiment starts; a post-treatment variable reintroduces exactly the bias it was meant to remove.

### Cursor object · `SQL`

A control structure that enables traversal over records returned by a query, behaving like a file handle: just as a program opens a file to reach its contents, it opens a cursor to reach a result set. It handles database queries, scrolling through the result set and retrieving results.

### cursor.execute() · `SQL`

The single entry point of a Python SQL interface such as `sqlite3`, performing any SQL command including retrieving data with a query like `"Select * from table_name."`. The result arrives as a collection of table data, typically a list of lists, which is why the same call creates tables, inserts rows and runs `SELECT`.

### Customer churn · `Analytics & BI`

The rate at which customers stop using a product or service over a period, and the event a retention model tries to predict. Because churn is defined by the business (a cancellation, an inactivity window, a non-renewal), the definition must be fixed before it is modelled.

### Customer lifetime value (CLV) · `Analytics & BI`

The expected profit a customer generates over the whole relationship, used to decide how much may be spent to acquire or retain one. It is a forward-looking estimate built from margin, retention rate and discounting, so its assumptions deserve more scrutiny than its point value.

### Cyclical Methodology · `Methodology`

The iterative framing of a data science project in which each stage informs the next and results feed back into earlier stages, so requirements, data and model are revisited rather than fixed once. Most real projects behave this way, and the phased frameworks are best read as checkpoints inside that loop.

---

## D

*113 terms*

### Dagster · `Data Engineering`

An orchestration framework that models pipelines as software-defined assets — the tables and files that should exist — rather than as opaque tasks, with typed inputs, schedules, sensors and built-in testing. It targets the maintainability problems that accumulate in large scheduled DAGs.

### Dash · `Library`

Open-source Python library for building reactive web applications: a Dash app is a web server running Flask and communicating JSON packets over HTTP requests, while the front end renders its components with React.js. Its two families are core components, higher-level interactive widgets, and HTML components, one per HTML tag.

### Dashboard · `Analytics & BI`

A single screen of coordinated charts and headline numbers answering a recurring set of questions for a defined audience. A good dashboard is designed around decisions and refreshes automatically; a bad one is a wall of charts nobody opens.

### Data Algorithms · `Concept`

Computational procedures and mathematical models applied to process and analyse data, made accessible in the cloud so they can be deployed against very large datasets without an organisation owning the infrastructure that runs them.

### Data Analysis · `Methodology`

The process of inspecting, cleaning, transforming and modeling data to discover useful information, draw conclusions and support decision-making. It is the umbrella term for the technical work that a methodology sequences into stages, from raw records through to a defensible conclusion.

### Data Asset eXchange (DAX) · `Cloud Platform`

IBM's curated catalogue of datasets, the data counterpart to the Model Asset eXchange. The naming mnemonic is models for MAX and data for DAX, and the pairing is what makes the two exchanges easy to keep apart.

### Data Asset Management (DAM) · `Data Governance`

The platform function that keeps an organisation's data assets findable and reusable: cataloguing what exists, versioning it, replicating and backing it up, and controlling who may read or change it. It is the operational machinery of governance — the policies say what should happen, and asset management is where it happens.

### Data augmentation · `Machine Learning`

The practice of expanding a training set by generating additional examples derived from the data already held, which is useful when labelled examples are scarce or a class is rare. The family of technique is chosen by data shape: the main ones are structured, semi-structured, image and audio data.

### Data catalogue · `Data Governance`

A searchable inventory of the datasets an organisation holds, describing each one's schema, owner, location, freshness, lineage and usage. It is what turns a data lake into something a newcomer can navigate rather than a set of directories whose names mean nothing.

### Data classification (sensitivity) · `Data Governance`

Labelling data by sensitivity — public, internal, confidential, restricted — so that handling, access, encryption and retention rules follow automatically from the label. Without it, protection is applied uniformly and therefore either too weakly or too expensively.

### Data Cleansing · `Data Engineering`

Identifying and correcting or removing wrong, inconsistent, duplicated or missing values before analysis. It is the least glamorous and usually the largest part of the work, and every change it makes should be recorded, because the decisions change downstream results.

### Data Collection · `Data Engineering`

The stage of gathering the records an analysis needs, from databases, APIs, files, sensors, surveys or scraping. What is collected is fixed by the data requirements, and decisions about volume, frequency and quality constrain every later stage.

### Data Compilation · `Data Engineering`

Gathering and organising material from several sources into one comprehensive dataset ready for analysis. It is the step between integrating separate sources and holding a single analysable table.

### Data contract · `Data Architecture`

An explicit, versioned agreement between a data producer and its consumers about schema, semantics, ownership, freshness and breaking-change policy. It moves integration failures from silent downstream breakage to a check that fails at the producer.

### Data drift · `MLOps`

A change in the distribution of the input features relative to what the model was trained on, such as a new customer segment or a shifted price range. It is detectable without labels, which makes it the earliest usable warning that a model's inputs no longer resemble its training world.

### Data engineering · `Data Engineering`

Turning raw data into information that an organisation can understand and use, through blending, testing and optimising data from numerous sources. The discipline covers the pipeline end of the work, where systems connect APIs, scraping routines and file formats, and hands a usable dataset to analysts.

### Data ethics · `Data Governance`

The reasoning about what uses of data are acceptable even when they are legal, covering consent, fairness, transparency and the power imbalance between the organisation holding data and the people in it. It is a judgement discipline, which is why it belongs in design reviews rather than in a policy document.

### Data Formatting · `Data Engineering`

Standardising data so it is uniform and easy to analyse, the third mechanical job of Data Preparation after handling missing values and removing duplicates. Formatting is treated as something to validate rather than silently rewrite, since a reformatted field can hide the defect that produced it.

### Data freshness · `Data Engineering`

How current a dataset is relative to the events it describes, usually stated as a target such as within one hour. It is a service level that must be agreed with consumers, because it drives cost, architecture and the whole batch-versus-streaming decision.

### Data governance · `Data Governance`

The set of policies, roles and controls that decide who may use which data, for what purpose, and who is accountable when it is wrong. It covers ownership, definitions, quality, privacy, access and retention, and its failure mode is an organisation that cannot answer where a number came from.

### Data granularity · `Data Engineering`

The level of detail at which each row of a dataset is recorded — one row per country, per city or per transaction. Finer granularity preserves variation that an aggregate hides while coarser granularity is smaller and less noisy, so the choice is a modelling decision that belongs with the results.

### Data ingestion · `Data Engineering`

Getting data from its sources into a platform, whether by a scheduled pull, a push from the source system, an API poll or a stream. The design choices are frequency, incremental versus full, schema handling and what happens when the source is late or malformed.

### Data Integration · `Data Engineering`

Merging data from several sources into one consistent dataset, removing redundancy on the way so that each fact is stored once. It is the plumbing between collection and analysis, and its failures show up much later as duplicated rows or contradictory values.

### Data lake · `Data Architecture`

A store that holds raw data in its native format — files, JSON, images, logs — until a use for it appears, usually on cheap object storage. Its failure mode is the data swamp: without a catalogue, schema discipline and ownership, a lake becomes an unqueryable dump.

### Data lakehouse · `Data Architecture`

An architecture that adds warehouse guarantees — schemas, transactions, time travel, fast SQL — on top of cheap object storage, so one copy of the data serves both analytics and machine learning. It is realised with open table formats such as Delta Lake and Apache Iceberg over Parquet files.

### Data leakage · `Machine Learning`

Information about the target leaking into training features or into validation data, which inflates measured performance so that the model appears excellent in testing and then contradicts real results. Common causes are a feature derived from the label, redundancy between features, and preprocessing such as scaling fitted before the data was split.

### Data lineage · `Data Governance`

The record of where a dataset came from and what it feeds — which sources produced it, which transformations ran and which downstream tables and dashboards depend on it. It is what makes impact analysis possible before a change, and root-cause analysis possible after a wrong number appears.

### Data Manipulation · `Data Engineering`

The process of transforming data into a usable format. It covers the range of adjustments applied between collection and analysis, so that values, columns and encodings match what a model or a report expects.

### Data mart · `Data Architecture`

A subset of a warehouse scoped to one department or subject area, such as finance or marketing. Narrow scope makes it fast to build and easy to understand, at the cost of duplicating data that another mart also needs.

### Data masking · `Data Governance`

Substituting realistic but false values for sensitive fields — a fake name, a scrambled card number — so non-production environments and analysts can work with the structure without seeing real identities. It must preserve the format and semantics the code depends on, or tests stop meaning anything.

### Data mesh · `Data Architecture`

An organisational pattern that treats data as a product owned by the domain team that knows it best, with each domain publishing discoverable, well-described datasets and a central platform supplying self-service infrastructure. It trades a central bottleneck for the harder problem of enforcing standards across many owners.

### Data Mining · `Data Engineering`

Automatically searching and analysing data to discover previously unknown patterns and insights, rather than confirming a hypothesis stated up front. It runs as a six-step process: set the goal, select data, preprocess, transform, mine, and evaluate, serving the purposes of deciding, predicting and understanding.

### Data Modeling · `Data Engineering`

The stage of a data science methodology in which data scientists develop models, either descriptive or predictive, that answer specific questions. Its declared end goal is that the data model answers the business question, which makes relevance to that question the test of the model rather than accuracy alone.

### Data observability · `Data Engineering`

Monitoring pipelines and datasets the way services are monitored: freshness, volume, schema change, distribution shift, null rates and lineage-aware alerting. It answers whether the data can be trusted right now, which a passing job status does not.

### Data ownership · `Data Governance`

The regime under which a dataset is held: private, meaning confidential, personal or commercially sensitive, or open, meaning publicly available under a public licence. The regime governs whether the data may be used at all, which is a separate question from whether it is technically accessible.

### Data pipeline · `Data Architecture`

The ordered set of steps that moves data from sources to a destination, with each step extracting, transforming, validating or loading. Pipelines are run on a schedule or on an event, and their two hard properties are idempotency and observability.

### Data Preparation · `Data Engineering`

The stage that turns raw data into the form an analysis or model needs: handling missing and invalid values, removing duplicates, fixing types and formats, engineering features and encoding categorical variables. It sits between data understanding and modelling, and it is where most project time goes.

### Data privacy · `Data Governance`

The set of legal and ethical constraints on collecting, using and sharing information about people, covering consent, purpose limitation, minimisation and the right to erasure. It constrains analysis at the design stage, since the permitted use of a dataset is decided before the data is gathered.

### Data product · `Data Architecture`

A dataset treated as a product: it has an owner, a documented schema, a service level, a version and consumers whose needs drive its roadmap. The framing exists to stop datasets from being published once and abandoned.

### Data Quality Assessment · `Data Governance`

Evaluating a dataset's integrity, accuracy and completeness by addressing missing, invalid or misleading values. Misleading is the hard criterion, because no completeness count or dtype check finds a value that is well formed and simply wrong.

### Data Replication · `Database`

Duplicating data across multiple nodes in a cluster so the data survives hardware failure and stays available for queries. The default replication factor is 3 with rack awareness, which tolerates a node or even a whole rack disappearing without data loss.

### Data Requirements · `Methodology`

Identifying and defining the data elements, formats and sources needed for a given analysis, downstream of the analytic approach. Requirements are revised rather than frozen, based on data availability, quality and content, so the list adapts as the data is inspected.

### Data retention · `Data Governance`

Rules that fix how long each class of data is kept and what happens at the end of that period, driven by legal obligation, cost and privacy minimisation. Retaining everything indefinitely is both a liability and a storage bill.

### Data Science · `Concept`

An interdisciplinary field that extracts insight and knowledge from data using programming, statistics and analytical tools. Its work follows a collect, analyse, interpret and decide cycle, and it borrows methods from computer science, statistics and the domain being studied.

### Data Science Methodology · `Methodology`

A structured approach to solving business problems with data analysis and data-driven insights, realised as a ten-stage cyclical framework: business understanding, analytic approach, data requirements, data collection, data understanding, data preparation, modeling, evaluation, deployment and feedback.

### Data Science Model · `Methodology`

The result of data analysis and modeling that provides answers to specific questions or problems. It is the object that deployment puts into use and that feedback assesses, and it is defined by what it produces rather than by what it is made of.

### Data Science Tool Categories · `Concept`

The seven families into which data science tools fall: data management; data integration and transformation; data visualization; model deployment, monitoring and assessment; data asset management; code development and execution; and code asset management. The families describe the job a tool does, not the vendor.

### Data Scientist · `Role`

The professional role that applies statistics, programming and domain knowledge to turn data into decisions — framing the question, gathering and cleaning data, modelling, evaluating and communicating the result. The title spans a wide range of practice, from analysis-heavy roles to research or engineering-heavy ones.

### Data set · `Data Engineering`

A collection of data treated as a unit for analysis, usually described by its structure (tabular, hierarchical, network or raw files), its size, its provenance and the licence under which it may be used. Two datasets with identical columns can still differ in meaning if their provenance or licence differs.

### Data set structures · `Data Engineering`

The three shapes a dataset takes: tabular, hierarchical or network, and raw files. Each shape implies a different access path, respectively a DataFrame, a nested or graph structure, and a parser plus metadata, so structure dictates how the data is read.

### Data silo · `Data Architecture`

A dataset or system held by one team or department and effectively inaccessible to the rest of the organisation. Siloes are usually organisational rather than technical, which is why integration projects fail when they are treated as purely technical.

### Data skew · `Data Engineering`

An uneven distribution of records across partitions or keys, so a few tasks process most of the data while the rest idle and a distributed job finishes no faster than its slowest partition. Salting keys, repartitioning or broadcasting the small side of a join are the standard remedies.

### Data SLA · `Data Engineering`

An agreed service level for a dataset or pipeline — when it will be refreshed, how complete it will be, how quickly failures are noticed and who is accountable. It is what makes an expectation enforceable rather than an assumption discovered at the monthly review.

### Data sovereignty · `Data Governance`

The requirement that data be stored and processed within a jurisdiction, subject to its laws. It forces architectural decisions about regions and replication, and it can prevent the simplest solution of consolidating everything in one central warehouse.

### Data steward · `Data Governance`

The role accountable for the meaning, quality and documentation of a domain's data, deciding definitions and resolving conflicts between teams. The role exists because a definition cannot be settled by whoever queries the table most often.

### Data Strategy · `Methodology`

A plan outlining how an organisation will collect, manage and use data to achieve its goals. It typically covers use cases, architecture, governance, talent, funding and ethics, which together decide what data work is possible rather than merely desirable.

### Data swamp · `Data Architecture`

A data lake that has become unusable: files of unknown provenance, no catalogue, no schema discipline and no owner. It is the standard failure mode of storing everything without governing anything.

### Data type · `Data Engineering`

The kind of value a variable holds and the set of mathematical, relational or logical operations that can be applied without causing an error. It predicts what `+` will do: `7 + 7` gives `14` while `"7" + "7"` gives `"77"`, and a column read from a file can silently be the wrong kind of thing.

### Data Understanding · `Methodology`

The methodology stage in which the collected data is explored and described — its variables, distributions, quality and gaps — to judge whether it can actually answer the business question. It is where a project usually discovers that the data it gathered is not quite the data it needs.

### Data versioning · `MLOps`

Tracking which exact snapshot of data produced a model, by hashing files, snapshotting tables or referencing a time-travel version. Without it, a model's lineage ends at the code, and the data that trained it can never be recovered.

### Data warehouse · `Data Architecture`

A central repository of structured, modelled data optimised for querying and reporting rather than for transaction processing. Loading it means agreeing on a schema, cleansing on the way in and keeping history, which is why it is trusted for decisions and slow to change.

### Database · `Database`

An organised collection of data held in a structured form so it can be stored, queried and updated efficiently. A database enforces constraints a spreadsheet cannot — types, keys and referential integrity — which is what keeps many users' changes from contradicting each other.

### Databricks · `Cloud Platform`

A unified data and AI platform built on Apache Spark by the team that created Spark, combining notebooks, Delta Lake tables, SQL warehouses and MLflow in one workspace. Its lakehouse design lets one copy of data serve both BI queries and model training, and its clusters separate compute from cloud object storage.

### Data-Driven Insights · `Concept`

Insights derived from analysing and interpreting data in order to inform decision-making. They are the output the whole methodology exists to produce, and their value is judged by the decision they change rather than by their sophistication.

### DataFrame · `Library`

pandas' two-dimensional labelled table: named columns that may hold different types, sharing one row index. It is the working object of most Python data analysis and the format that `read_csv`, `read_sql`, `groupby` and the plotting methods all speak.

### Dataiku · `Cloud Platform`

A collaborative data science and AI platform that mixes visual recipes with code, aimed at teams where analysts and engineers work in the same flow. Its value is the governance around shared projects rather than any single algorithm.

### DataOps · `Data Architecture`

The application of software-engineering practice to data pipelines: version control, code review, automated testing, CI/CD, monitoring and reproducible environments. It is what turns a collection of scripts into something a team can maintain.

### DataRobot · `Cloud Platform`

An enterprise automated machine-learning platform that builds, compares and deploys models from a prepared dataset with limited code. It shortens the path to a baseline, and its risk is producing models no one on the team can explain.

### Dataset licence · `Data Governance`

The instrument stating whether a dataset may be used and under what guidelines. Every licence answers four questions, covering use, modification, redistribution and share-alike, with attribution and non-commercial conditions recurring, so a technically readable file is not automatically usable.

### Date and time functions · `SQL`

SQL functions for extracting components from temporal values, with the forms `DATE`, `TIME`, `TIMESTAMP`, `YEAR`, `MONTH`, `DAY`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `HOUR`, `MINUTE` and `SECOND`, plus `CURRENT_DATE`, `CURRENT_TIME`, `DATE_ADD`, `DATE_SUB`, `DATEDIFF` and `FROM_DAYS`. They answer questions such as `select DAY(RESCUEDATE) from PETTABLE where ANIMAL = 'cat'`.

### DBA (Database Administrators) · `Role`

Professionals responsible for managing databases and extracting data from them. The role boundary runs between the data scientist, who states the data requirement, and the DBA, who performs the extraction and integration that satisfies it.

### DBSCAN · `Machine Learning`

A density-based spatial clustering algorithm that creates clusters using a density value supplied by the user. Because it defines clusters as regions of relatively high density rather than as proximity to a centroid, it works well with natural patterns and can leave low-density points unassigned.

### dbt (data build tool) · `Data Engineering`

An analytics-engineering tool that turns SQL `SELECT` statements into a dependency-ordered, tested and documented model graph, materialised as tables or views in the warehouse. It brings version control, automated testing and generated documentation to the transformation layer, which is where most warehouse logic actually lives.

### DDL — Data Definition Language · `SQL`

The statement family that defines, changes or drops data structures: `CREATE`, `ALTER`, `TRUNCATE` and `DROP`. It changes structure rather than rows: `CREATE` adds an object, `ALTER` changes one, `DROP` removes it together with a table's rows, and `TRUNCATE` removes all rows while keeping the definition.

### Decision Trees · `Machine Learning`

A machine learning algorithm that makes decisions through a tree-like structure of successive splits, each split chosen on the feature and threshold that most reduces impurity as measured by Gini or entropy. Each root-to-leaf path is a conjunction of conditions, which makes the model readable as a rule set.

### Deep Learning · `Machine Learning`

A subset of machine learning that uses layered artificial neural networks inspired by the brain. The stacked layers let the model learn representations and make complex decisions from data on its own, at the cost of needing far more data and compute than a shallow method.

### Deeplearning4j · `Library`

A deep learning library built with Java, for neural networks inside the JVM. It is the option when a model must be embedded in an existing Java service and the surrounding deployment stack cannot host a Python runtime.

### del (for a list element) · `Python`

A statement, not a method, that deletes the object of a list at a specified index, as in `del(my_collection[2])`. It removes the item in place, shifts the following elements left, returns nothing, and also accepts a slice such as `del L[1:3]` or a whole name such as `del L`.

### DELETE FROM … WHERE · `SQL`

A statement that removes rows matching a predicate, as in `DELETE FROM Instructor WHERE lastname = 'BORRAR'`, leaving the table and its schema intact; `DELETE FROM t;` empties it. SQLite accepts single quotes for string literals and double quotes for identifiers, so a misspelled quoted name can be silently reinterpreted.

### Delimiter · `Data Engineering`

A character or sequence of characters used to separate or mark the boundaries between elements or fields within a larger structure such as a string or a file. Every tabular file format is defined by its delimiter, and `split(delim)` is where parsing starts.

### Delta Lake · `Data Architecture`

The open table format created with Databricks that adds a transaction log over Parquet files, providing ACID writes, time travel, schema enforcement and unified batch and streaming. It is the storage layer that makes a lake behave like a warehouse table.

### Denormalisation · `Data Architecture`

Deliberately duplicating data or flattening tables to avoid joins at query time. It is the standard trade in analytical stores and columnar warehouses, where storage is cheap and repeated reads are expensive, but it puts the burden of keeping copies consistent on the pipeline.

### Derived tables · `SQL`

A sub-query placed in the `FROM` clause, so the outer query uses the results of the sub-query as its data source; also called a table expression. Treating a result set as a table is what makes questions such as the average salary of the top five earners answerable.

### Descriptive Approach · `Methodology`

The analytic approach that answers what the current status is, showing relationships and identifying clusters based on events and preferences. Its techniques are data aggregation, data mining and data visualization, and it describes rather than explains.

### Descriptive Model · `Methodology`

A model that examines relationships between variables and makes inferences based on observed patterns, with inferences being the word that separates it from mere description. It is one of the two possible outcomes of the modeling stage, the other being a predictive model.

### Descriptive Statistics · `Statistics`

Summary measures that condense a variable into a few numbers — mean, median, minimum, maximum, standard deviation and counts — or into a distribution such as a histogram. They are the first look at any dataset and the fastest way to spot a wrong scale, a skew or a missing block of values.

### df.describe() · `Library`

Pandas' statistical summary of a dataset: `df.describe()` defaults to numerical columns only, while `df.describe(include="all")` produces a summary across all variables. The default silently omits categorical columns, so a summary that looks complete can hide the text fields.

### df.dtypes · `Library`

Pandas attribute returning the data type of every column in a data frame, written `df.dtypes`. Pandas has its own types such as `object`, `float`, `Int` and `datetime`, so the check is worth running before arithmetic, because a numeric column stored as `object` fails or misbehaves later.

### df.info() · `Library`

Pandas method that retrieves a summary of the data frame being used, written `df.info()`. It reports the columns, their non-null counts and their dtypes together, which makes it the quickest single call for spotting both the wrong type and a partly empty column.

### df.isnull() · `Library`

Pandas method returning a Boolean frame marking every missing value, used as `missing_data = df.isnull()` and then summarised per column with `missing_data[column].value_counts()`. Quantifying missingness before deciding how to handle it is the habit the step establishes, because cleaning blind discards information that the counts would have justified keeping.

### df.to_sql() · `Library`

A pandas method that writes the contents of a DataFrame into a SQL database table, structurally storing the data, with the syntax `df.to_sql('table_name', index=False)`. The full signature is `to_sql(name, con, if_exists=, index=, method=)`, where `if_exists` decides whether an existing table is replaced or appended to.

### Diagnostic Analysis · `Methodology`

The analytic approach that answers why something happened, classified as statistical analysis. Its techniques are drill-down, data discovery and correlation analysis, and it moves from a symptom observed in the data towards the mechanisms that generate it.

### Dictionaries · `Python`

A data structure storing a collection of key-value pairs, where each key is unique and associated with a specific value, giving a flexible way to store and retrieve data based on unique keys. It is the shape of labelled data and the step between a list of values and a table's row.

### Dictionary keys and values · `Python`

The `keys()` method returns a view object displaying all the keys of a dictionary in order of insertion, and the pairs it holds link each key to a value. Keys necessitate immutability and uniqueness, so an unhashable or already-used key cannot be added, while values carry no such restriction.

### Diffusion model · `Generative AI`

A generative model that learns to reverse a gradual noising process, starting from random noise and denoising step by step into an image or audio sample. Text-to-image systems are conditioned diffusion models, and the iterative process is why generation is slower than a single forward pass.

### Digital Change · `Concept`

Integrating digital technology into business processes and operations to improve how an organisation operates and delivers value. It is incremental and process-level, changing how existing work is done rather than redefining what the organisation does.

### Digital Transformation · `Concept`

A strategic and cultural organisational change driven by data science, especially big data, in which digital technology is integrated across all areas and fundamentally changes operations and value delivery. It is broader than process-level digital change, since it alters the organisation's strategy and culture, not only its tooling.

### Dimension table · `Data Architecture`

A table describing the entities a fact can be grouped by: customer, product, store, date. Dimensions carry the descriptive columns used in filters and labels, and their keys are what a fact table joins on.

### Directed acyclic graph (DAG) · `Data Architecture`

A set of tasks connected by dependencies with no cycles, so there is always a valid execution order. Workflow schedulers such as Airflow represent a pipeline as a DAG, which is what lets them run independent tasks in parallel and skip everything downstream of a failure.

### Discrimination Criterion · `Statistics`

A measure used to evaluate how well a model classifies different outcomes, and the quantity that the ROC curve is produced by varying. That varied quantity is the decision threshold or score cut-off, so the criterion is the knob rather than the curve.

### DISTINCT · `SQL`

A keyword that de-duplicates projected rows, returning the unique values of the listed columns as combinations; inside an aggregate it de-duplicates before counting, as in `SELECT COUNT(DISTINCT Release_Year)`. `DISTINCT` shapes the result while `COUNT(DISTINCT …)` counts it, and the aggregate form ignores `NULL`s.

### Distributed Data · `Data Engineering`

Dividing data into smaller chunks and distributing them across multiple computers in a cluster, which enables parallel processing. The split is what allows a computation to scale past one machine, and it also means any operation needing a global view must gather results back together.

### Distributed Version Control System (DVCS) · `Tool`

A version-control system in which every user holds a complete copy of the project and its full history. Work continues offline, and synchronisation happens between peers rather than against a single central server, so no single machine is a point of failure for the history.

### DML (Data Manipulation Language) · `SQL`

Statements used to read and modify data, with the command list `Create`, `Insert`, `Select`, `Update` and `Delete`. The DML and DDL split decides which statements change data and which change structure, the distinction that makes a `DELETE` recoverable from backup while a `DROP` is a schema event.

### Docker · `MLOps`

A tool that packages an application with its libraries and system dependencies into a portable image, so it runs identically on a laptop, a CI runner and a cluster. It removes the environment as an explanation for a difference between two machines.

### Docstrings · `Python`

Documentation strings enclosed in three quotes that describe what a function does and how to use it. Writing them keeps code clear, organised and maintainable, and the `help` command returns the documentation defined for a particular function, making the docstring the fastest lookup available in an interactive session.

### Domain Knowledge · `Concept`

Expertise and understanding of a specific subject area, including its concepts and its relevant data. It is the input that makes feature engineering possible and the difference between a model that is statistically valid and one that is plausible, since it supplies the variables and the constraints a purely statistical choice would miss.

### Dot notation · `Python`

The syntax for interacting with objects by calling their methods or accessing their attributes, written `obj.attribute` and `obj.method()`. It is the syntax of the whole library ecosystem, so `df.head()` performs the same kind of operation as `car1.accelerate(30)`.

### Dot product · `Statistics`

The sum of the element-wise products of two arrays, used for vector and matrix operations to find the scalar result of multiplying corresponding elements and summing them. It is listed under matrix multiplication in Python and called as `np.dot(matrix1, matrix2)`.

### dplyr · `R`

The R library for manipulating data, organised as one function per verb: `filter`, `select`, `mutate`, `arrange`, `group_by` and `summarise`, composed with a pipe. The verbs form R's data-wrangling grammar, mirroring how SQL separates filtering, projection and aggregation.

### Drill-down · `Analytics & BI`

Moving from an aggregate to the detail beneath it — from annual revenue to quarters, then months, then orders — along a defined hierarchy. It is how an anomaly found at one level is traced to its cause at another.

### dropna() · `Library`

Pandas method that removes missing values, where `axis=0` drops the row and `axis=1` drops the column holding them, for example `df.dropna(subset=['price'], axis=0, inplace=True)`; `inplace` writes the result back into the data frame. Dropping rows leaves the index with gaps, so it is usually reset afterwards.

### DuckDB · `Data Engineering`

An in-process analytical database that runs inside a Python or R session with no server, executing fast columnar SQL directly on local files, Parquet and DataFrames. It brings warehouse-grade analysis to a single machine, and it is often the fastest way to test a pipeline's logic.

---

## E

*18 terms*

### Early stopping · `Machine Learning`

Halting training when validation performance stops improving, keeping the best checkpoint rather than the last one. It is the simplest regulariser available, and it requires a validation set that was not used for anything else.

### Effect size · `Statistics`

A measure of how large a difference or relationship is, expressed in units that do not depend on sample size, such as Cohen's d or a correlation coefficient. It separates statistical significance from practical importance, since significance can be bought with sample size alone.

### Elasticsearch · `Database`

A distributed RESTful search engine and analytics tool built on Lucene, offering full-text search, real-time indexing and aggregation over JSON documents. It is reached over HTTP rather than SQL, and its aggregation layer makes it usable for analysis as well as lookup.

### ELT (Extract, Load, Transform) · `Data Engineering`

Extract from sources, load the raw data into the target warehouse as-is, then transform it with SQL where it now sits, keeping the raw layer queryable and the transformations re-runnable. It inverts ETL: an ETL pipeline transforms on the way in, an ELT pipeline preserves the raw copy and pushes transformation into the warehouse's own compute.

### Embedding · `Generative AI`

A dense numeric vector that represents the meaning of a text, image or record in a space where similar items sit close together. Embeddings make semantic search and clustering possible, and they are the retrieval primitive underneath most knowledge-grounded AI applications.

### Endpoint · `Web & APIs`

The specific URL at which a resource is reached, so the concrete artefact an integration is built against rather than the service as a whole. An endpoint names the address, the resource path, and implicitly the operation available there. Changing the URL breaks every client that hard-coded it.

### Ensemble learning · `Machine Learning`

Combining several models so their errors partly cancel, which almost always beats the best single model on tabular data. Averaging many high-variance models is bagging; fitting models sequentially so each corrects the last is boosting.

### Entity-relationship (ER) model · `Database`

A data model that treats a database as a collection of entities, bridging a domain description and a physical schema by deciding what things exist before deciding what columns they have. The diagram convention is explicit: entities become rectangles and tables, attributes become ovals and columns. Deferring attributes until the entity list is stable prevents redundant tables.

### enumerate() · `Python`

A Python built-in that adds a counter to an iterable, letting a loop walk through both the elements and their indices without maintaining a manual counter variable such as `i = i + 1`. It returns pairs, so `for i, item in enumerate(items):` is the idiomatic form. The optional `start` argument sets where numbering begins.

### Escape sequence · `Python`

Two or more characters that typically begin with an escape character and instruct the computer to perform a function or command instead of printing literally. A backslash marks that the character immediately following it is treated specially, whether escaped or as part of a raw string. Forgetting to escape a backslash inside a Windows path mangles the string.

### ETL (Extract, Transform, Load) · `Data Engineering`

The classic data-warehousing integration pattern in which data is extracted from sources, transformed into a consistent analytic shape, then loaded into the target store. It arranges the heavy work before the load, keeping the destination clean and query-ready. Its modern variants are ELT, which transforms inside the target, and streaming pipelines.

### Event streaming · `Data Engineering`

Treating each change as an immutable record published to an ordered log, which many consumers read independently at their own pace. It inverts the batch model of asking the source for state, and it is what makes event-driven pipelines and change data capture possible.

### Exceptions and exception handling · `Python`

A Python mechanism for gracefully managing and responding to errors or exceptional conditions that occur during program execution, so they do not crash the program. Failures arrive from files, API responses and user input alike, and an unhandled one halts execution at that line. Catching an exception you cannot act on is worse than letting it surface.

### Executive summary · `Methodology`

A section usually placed at the beginning of a research paper that summarises its important parts, including the key findings. In practice it carries the finding, its implication and the recommended action. Readers who stop after it should still be able to act correctly, so burying the finding later defeats its purpose.

### Experiment tracking · `MLOps`

Recording what was run and what came out — code version, data version, hyperparameters, metrics, artifacts — so a result can be compared with another and reproduced later. Without it, model selection reduces to whoever remembers the best number.

### Explainable AI (XAI) · `Data Governance`

Methods that make a model's decisions intelligible to people — feature attributions, surrogate models, decision rules, counterfactual explanations. It exists because a high-accuracy model that cannot be justified is unusable in regulated or high-stakes decisions.

### Exploratory Data Analysis (EDA) · `Methodology`

The visual and statistical exploration of a cleaned dataset, covering distributions, missingness, outliers, correlations and group comparisons, performed before modelling. It establishes what the data actually contains rather than what it was assumed to contain. Skipping it usually means discovering a broken variable after the model is already fitted.

### Expression · `Python`

A combination of operators and operands that is interpreted to produce some other value, the smallest unit of computation. Operands are values or names, and nested expressions evaluate innermost first, so everything right of an `=` is resolved before binding. `a + b`, `x * y + 1` and `len(my_string) > 3` are all expressions.

---

## F

*29 terms*

### F1 score · `Machine Learning`

The harmonic mean of precision and recall, high only when both are high. It forces a single number onto a trade-off that matters asymmetrically, so it is the right summary when neither kind of error is clearly more costly and the wrong one when they are.

### Fact table · `Data Architecture`

The table at the centre of a dimensional model, holding the measurements of a process — sales amount, quantity, duration — plus foreign keys to the dimensions that describe them. Facts are numeric and additive; everything you group by lives in a dimension.

### factor · `R`

R's data type for categorical variables, storing values as integer codes alongside a `levels` attribute, where the first level serves as the baseline in models. It is applied before plotting or fitting, as in `as.factor(mtcars$vs)`. Level order decides the baseline, so releveling changes coefficients and axis labels.

### False-Positive Rate · `Statistics`

The rate at which a model incorrectly identifies negative outcomes as positive, computed as `FP / (FP + TN)`, equivalently `1 − specificity`. It forms the x-axis of the ROC curve, and the relative cost of the two error types determines how far along that curve it is worth operating. Threshold choice is a business decision, not a modelling one.

### Fast-forward merge · `Tool`

The merge Git performs when the target branch is an ancestor of the source branch, so the branch pointer simply advances. History stays linear with no merge commit created. Because no commit records the integration, undoing it means moving the pointer back rather than reverting a merge.

### Feast · `MLOps`

An open-source feature store that defines features once and serves them both from an offline store for training and an online store for prediction, keeping the two consistent. It is the concrete implementation of the train-serve consistency principle.

### Feature · `Machine Learning`

A characteristic or attribute within the data that helps solve the problem, making it problem-relative by definition: an attribute is a feature only if it helps answer this particular question. The same column can therefore be a feature in one task and noise in another. Feature selection follows from that framing rather than from the column list.

### Feature Engineering · `Machine Learning`

Creating new features or variables based on domain knowledge in order to improve the performance of machine learning algorithms. It treats data preparation as a thinking stage rather than a cleaning stage, since the new variable encodes something the model could not derive alone. Ratios, time since an event and aggregates over windows are typical products.

### Feature Extraction · `Machine Learning`

Identifying and selecting relevant features or attributes from the dataset. It is the sibling of feature engineering: extraction selects among what exists while engineering creates something new, and conflating them hides the difference between removing noise and adding signal. Both reduce the input space, but only one changes what information is available.

### Feature Importance · `Machine Learning`

A reading of which factors contribute most to a model's predictions. On a fraud classifier it turns the model into prevention patterns, naming signals such as unusually large purchases, transactions from unfamiliar locations, rapid repeated purchases and abnormal spending behavior. Importance describes the fitted model, not the causal effect of the variable.

### Feature selection · `Machine Learning`

Choosing which input variables to keep, by filter methods that score each feature independently, wrapper methods that search subsets, or embedded methods such as Lasso that shrink coefficients to zero. Fewer, better features reduce overfitting, training time and the cost of explaining the model.

### Feature store · `MLOps`

A system that computes features once and serves them both to training jobs offline and to prediction requests online, keeping the two definitions identical. It exists to prevent training-serving skew, the failure in which a model is trained on features computed one way and scored with features computed another.

### Few-shot prompting · `Generative AI`

Including a handful of worked examples in the prompt so the model infers the pattern, the label set and the output format. Two or three well-chosen examples often lift accuracy more than paragraphs of instruction, and the examples are effectively a form of training at inference time.

### File attribute · `Python`

Either a property or metadata associated with a file and managed at the operating system level, or, in a coding context, an attribute of the file object you opened, reached through `file1.name` and `file1.mode`. Reading and processing such an object is what the phrasing usually means in practice. Keeping the two senses apart avoids confusing permissions with object state.

### File formats and extensions · `Data Engineering`

The structure and encoding rules used to store data in files, such as `.txt` for plain text or `.csv` for comma-separated values. The extension signals what type of file it is and what it needs to open with, while CSV, XML, JSON and xlsx are common in code. An extension is a convention, not proof of contents.

### File modes · `Python`

The modes control whether a file is opened for reading, writing or appending, each with its own failure behaviour: `'r'` opens an existing file and raises an error if it does not exist, `'w'` creates a new file and overwrites any existing one, and `'a'` appends data at the end. Choosing `'w'` when you meant `'a'` destroys the file silently.

### File pointer · `Python`

The position inside an open file where the next read or write begins, tracked in bytes. `tell()` reports the current position, `seek(offset, from)` moves it by an offset relative to `0`, `1` or `2` for the beginning, current position or end, and `truncate()` cuts the file there. Reads and writes that ignore the pointer yield surprising content.

### find() versus find_all() · `Library`

In HTML parsing, `find()` returns particular tag content while `find_all()` returns a list of all matching tags. One returns a node and one returns a list, and which you hold decides whether you navigate or iterate, since `[n]` subscripts the list but raises `TypeError` on the node. Typical calls are `soup.find('table')`, `soup.find_all("tbody")[1]` and `soup.find("h3", {"id": "Most_densely_populated_countries"})`.

### Fine-tuning · `Generative AI`

Further training a pretrained model on task-specific or domain-specific examples so it adopts a style, format or specialisation. It changes behaviour rather than adding knowledge, is more expensive and less reversible than prompting, and requires a held-out set to prove it helped.

### Fivetran · `Data Engineering`

A managed extract-and-load service that keeps connectors to hundreds of sources in sync with a destination warehouse, handling schema drift, incremental syncs and retries. It removes the maintenance of bespoke ingestion scripts, and it deliberately stops at load, leaving transformation to SQL or dbt.

### Float · `Python`

A floating-point number, that is, a number carrying a decimal point such as `y = 12.4`, or a number or numeric string converted into that type. Division of two integers returns a float, and it is the type whose imprecision breaks naive equality tests. IEEE-754 binary representation means most decimal fractions have no exact binary form.

### Folium · `Library`

A Python library for building interactive maps, where the pattern is map to children: `add_child()` attaches each `Circle`, `Marker` and `Popup` to the map. A `Popup` is added to the feature it annotates rather than to the map itself. Building features before attaching them keeps the layering readable.

### for loop · `Python`

A loop that iterates over a sequence, such as a list, tuple or string, executing a block of code once for each item. It is the idiomatic Python loop because you iterate the data rather than an index, though `for i in range(0,5):` remains valid when a counter is wanted. Mutating a container while iterating it skips elements.

### Fork · `Tool`

A copy of a repository made server-side into your own account, allowing a contributor without write access to propose changes back to the original. It sits at the start of the external contribution workflow, ahead of the pull request. Keeping a fork synchronised with upstream is the ongoing maintenance cost it introduces.

### Foundation model · `Generative AI`

A large model pretrained on broad data that is meant to be adapted to many downstream tasks by prompting or fine-tuning rather than trained from scratch. The economic point is that one expensive pretraining run is amortised across countless applications.

### Foundational Methodology · `Methodology`

A cyclical, iterative data science methodology consisting of ten stages, starting with Business Understanding and ending with Feedback, and followed as a prescribed sequence. The fixed stage list makes the process auditable and teaches the order of the work. Real projects often revisit early stages, which the loop permits while the sequence does not.

### Function calling · `Generative AI`

A model capability to emit a structured request to call a named function with typed arguments, which the application then executes and returns as an observation. It is how a model reaches databases, APIs and code, and it converts free text into something a program can act on safely.

### Functions · `Python`

Reusable code blocks that perform specific tasks, take input parameters and often return results, enhancing code modularity and reusability. A function is where a repeated operation becomes a name, and where a bug is fixed once instead of five times. Prefer returning a value over printing one, so the call can be composed.

### Funnel analysis · `Analytics & BI`

Measuring the proportion of users who progress through an ordered sequence of steps — visit, sign up, activate, purchase — and locating where the largest drop occurs. It converts a conversion rate into a specific step to fix.

---

## G

*27 terms*

### GDPR · `Data Governance`

The European Union's General Data Protection Regulation, which establishes lawful bases for processing personal data, requires transparency and data minimisation, grants rights of access, correction and erasure, and imposes penalties for breaches. It shapes pipelines that touch EU residents wherever the company is based.

### Generative Adversarial Networks (GANs) · `Generative AI`

A generative architecture in which a generator produces samples and a discriminator distinguishes them from real data, with the two trained adversarially. The discriminator's judgement supplies the learning signal that pushes the generator toward realistic output, and neither network is useful alone. Training instability is the price of that opposition.

### Generative AI · `Generative AI`

A subset of AI focused on creating new data, including images, music, text and code, rather than only analysing existing data. The output is synthesised content, which distinguishes it from predictive modelling that labels or scores existing records. Verifying generated output against reality remains the user's responsibility.

### GGally and ggpairs() · `Library`

GGally is an R package whose `ggpairs()` function draws a scatterplot matrix of several variables at once, including the iris variables coloured by species. It delivers exploratory visual analysis of pairwise relationships at a glance. With many variables the grid becomes unreadable, so it suits a handful of columns.

### ggplot2 · `R`

R's grammar-of-graphics plotting library, in which a plot is data plus an `aes()` mapping plus `geom_*()` layers composed with `+`. Titles and labels are added with `ggtitle`, `labs` and `theme`. The grammar makes a plot a composable object, so layers can be reordered or replaced without rewriting it.

### Git · `Tool`

The distributed version control system that tracks changes through a content-addressed object store of blobs, trees, commits and refs, and is the de facto standard for code asset management. Every clone carries the full history, so most operations work offline. Because history is content-addressed, rewriting published commits breaks other people's clones.

### git reset · `Tool`

The command that moves the branch pointer to another commit, with `--soft` keeping changes staged, `--mixed` keeping them in the working tree, and `--hard` destroying them. It is safe only on unpushed work, since rewriting shared history forces everyone else to recover. Reach for `--hard` last, and check the target commit twice before running it.

### git revert · `Tool`

The safe undo: it adds a new commit that reverses an earlier commit's changes, preserving history so the correction can be shared. Unlike a history rewrite, it is safe on a branch others have already pulled. It requires a clean working tree and can conflict when later commits touch the same lines.

### GitHub · `Tool`

One of the most popular web-hosted services for Git repositories, adding issues, pull requests, reviews, Actions and Projects on top of the Git protocol. The hosting layer is what turns a local version control system into a collaboration platform. Repository visibility and access tokens are the settings that most often cause surprises.

### GitLab · `Tool`

A DevOps platform delivered as a single application, providing Git repository access and source code management with built-in Continuous Integration and Continuous Delivery. Because the pipeline runs from the same application, repository and CI configuration stay in one place. Self-hosting is a supported deployment, unlike purely hosted alternatives.

### Google BigQuery · `Cloud Platform`

Google's serverless, columnar, multi-tenant data warehouse that runs standard SQL over petabyte-scale tables without any cluster to size or patch. Storage and compute are billed separately, and partitioning plus clustering are the two levers that keep scanned bytes — and the bill — down.

### Google Cloud Dataflow · `Cloud Platform`

Google's managed runner for Apache Beam pipelines, supporting the same code in batch and streaming mode with automatic scaling of workers. Streaming and batch being one API is its main conceptual advantage.

### Google Cloud Platform (GCP) · `Cloud Platform`

Google's cloud platform, whose data stack centres on BigQuery, Cloud Storage, Dataflow, Pub/Sub and Vertex AI. It is often chosen where BigQuery's serverless SQL model or Google's machine-learning tooling is the deciding factor.

### Google Cloud Pub/Sub · `Cloud Platform`

Google's managed publish-subscribe messaging service, decoupling producers from consumers with at-least-once delivery and per-subscription retention. It is the ingestion front door for streaming pipelines on GCP.

### Google Cloud Storage (GCS) · `Cloud Platform`

Google's object storage service, organised into buckets with storage classes that trade retrieval latency for price. It is the persistence layer beneath BigQuery external tables, Dataflow and Vertex AI training jobs.

### Google Colaboratory (Colab) · `Tool`

A free Jupyter notebook environment running entirely in the cloud, with notebooks executed in the browser, projects stored on Google Drive and GitHub, and most machine learning and visualization libraries pre-installed. It removes local installation work, and it is a zero-install way to obtain a GPU. Sessions are ephemeral, so anything not saved to the drive is lost.

### Google Vertex AI · `Cloud Platform`

Google's unified machine-learning platform, covering datasets, training, pipelines, a model registry, endpoints and evaluation, with Gemini models reachable through the same interface. It is the successor to the separate AI Platform and AutoML services.

### GPU · `Data Engineering`

A graphics processing unit, the hardware accelerator whose parallel arithmetic throughput decides whether a model trains in hours or weeks. It performs the large matrix operations behind neural network training far faster than a CPU. Memory capacity on the card, not raw speed, is often what limits batch size.

### Gradient boosting · `Machine Learning`

An ensemble built by fitting each new tree to the residual errors of the current ensemble, so the model improves stage by stage under a small learning rate. It usually wins on structured data, and it will overfit if the number of trees is not controlled by early stopping.

### Gradient descent · `Machine Learning`

An iterative optimiser that moves parameters opposite the gradient of the loss, scaled by a learning rate, until the loss stops improving. Stochastic and mini-batch variants use subsets of the data per step, which makes training on large datasets feasible and adds useful noise.

### Grafana · `Analytics & BI`

An open-source dashboarding platform aimed at operational time-series data, querying sources such as Prometheus, InfluxDB, Elasticsearch and SQL and alerting on thresholds. It answers what is happening right now, which is a different question from a monthly business dashboard.

### GraphX · `Library`

Spark's graph-processing component, representing a property graph as two typed RDDs holding vertices and edges, with a Pregel-style iterative message-passing API. It brings graph algorithms into the same engine as the rest of a Spark pipeline. The RDD API is lower-level and less convenient than the DataFrame-based GraphFrames alternative.

### Great Expectations · `Data Engineering`

A data-quality framework in which expectations — column values fall in a range, keys are unique, nulls stay under a threshold — are declared as code and validated in the pipeline. A failed suite stops the pipeline instead of publishing bad data, which is the point of testing data rather than only code.

### GridSearchCV · `Machine Learning`

A scikit-learn object that exhaustively evaluates hyperparameter combinations by cross-validating each candidate, replacing a hand-written loop. Typical use passes a grid such as `parameters = [{'alpha': [0.001, 0.1, 1, 10, 100, 1000, 10000]}]` with `cv=4`, fits, then reads `best_estimator_`, as in `GridSearchCV(Ridge(), parameters, cv=4)`. Tuning on folds rather than the test split stops the search overfitting the test set.

### GROUP BY · `SQL`

A SQL clause that groups a result into subsets sharing matching values for one or more columns. It contrasts with deduplication: `SELECT DISTINCT (country) FROM Author` removes duplicate countries, whereas `SELECT country, COUNT (country) FROM Author GROUP BY country` also reports how many authors come from each. Every selected column must be aggregated or listed in the group by.

### groupby() · `Library`

The pandas method that splits a frame by one or more keys and applies an aggregation per group, as in `df_group_one.groupby(['drive-wheels'], as_index=False).agg({'price': 'mean'})` or `df_gptest.groupby(['drive-wheels','body-style'], as_index=False).mean()`. It converts a categorical column into a comparison, answering what the mean price is per group rather than overall. That per-group question is what identifies a useful predictor.

### Guardrails · `Generative AI`

Checks placed around a model's inputs and outputs — validation, allow-lists, content filters, grounding requirements — to catch unsafe, off-topic or malformed results. They exist because a probabilistic system cannot be made reliable by instruction alone.

---

## H

*22 terms*

### H2O Driverless AI · `Cloud Platform`

A commercial AutoML platform covering the complete data-science life cycle, listed among both commercial development environments and cloud fully-integrated tools. It automates model building and feature work end to end. Licensing cost and limited control over the internal pipeline are the usual trade-offs.

### Hadamard product · `Statistics`

A mathematical operation performing element-wise multiplication of two matrices or arrays of the same shape, producing a new matrix in which each element is the product of the corresponding elements in the inputs. Multiplication of two arrays corresponds to this element-wise product, and it is what the `*` operator performs. It is not matrix multiplication, and shapes must match.

### Hadoop · `Data Engineering`

An open-source distributed storage and processing framework for large datasets, comprising HDFS for storage, MapReduce for batch compute, YARN for scheduling and Common for shared libraries, all implemented in Java. It made commodity-hardware clusters a viable platform for data at scale. Disk-based MapReduce makes it ill-suited to low-latency or interactive queries.

### Hadoop Distributed File System (HDFS) · `Data Engineering`

The storage system within Hadoop that partitions and distributes files across multiple nodes for parallel access and fault tolerance. A NameNode holds the metadata while DataNodes store blocks, with a default block size of `128 MB` and a replication factor of `3`. The single NameNode is the historical availability bottleneck.

### Hallucination · `Generative AI`

A confident, fluent output that is factually wrong or unsupported by any source. It is a consequence of generating plausible text rather than retrieving verified facts, which is why grounding, citation and human review are part of any deployment that matters.

### HAVING · `SQL`

A SQL clause used in combination with `GROUP BY` to filter aggregated results, as in `SELECT country, COUNT (country) AS CONTEO FROM AUTHOR GROUP BY country HAVING COUNT (country) > 4`. `WHERE` filters rows before grouping while `HAVING` filters groups after aggregation. Using the wrong one answers a different question, and aggregates belong in `HAVING`, never in `WHERE`.

### HDBSCAN · `Machine Learning`

A variant of DBSCAN that requires no parameters to be set and instead uses cluster stability, defined as the persistence of a cluster over a range of distance thresholds. It improves on DBSCAN by handling clusters of varying density. It can be slower than DBSCAN, and points left unassigned are treated as noise rather than forced into a cluster.

### head() and tail() · `Library`

pandas methods printing the first or last few entries of a data frame, `df.head(n)` and `df.tail(n)`, where `n` defaults to `5` and each returns a new frame without modifying the original. They are the cheapest correctness check available, and on a frame read with `header=None` they expose numeric labels such as `0 1 2 3` where column names should be.

### Hierarchical clustering · `Machine Learning`

A clustering approach that can be divisive, working top-down, or agglomerative, working bottom-up, and that produces a dendrogram to visualize the cluster hierarchy. The agglomerative variant repeatedly merges the closest clusters, so the dendrogram records every merge and its distance. Cutting the dendrogram at a chosen height selects the number of clusters.

### High-performing computing (HPC) cluster · `Data Engineering`

A computing technology using a system of networked computers to solve complex, computationally intensive problems in traditional environments. Such clusters are tightly coupled with a low-latency interconnect and typically use MPI, which suits compute-bound work. It addresses a different bottleneck from loosely coupled big-data platforms, which scale data volume rather than floating-point throughput.

### Histogram · `Visualization`

A graphical representation of the distribution of a dataset in which the data is divided into intervals or bins and the height of each bar gives the frequency of points in that interval. It is the fastest answer to whether the data is representative. Bin width changes the picture, so an apparent gap may be an artefact of that choice.

### HTML · `Web & APIs`

The Hypertext Markup Language, the standard language for creating and structuring content on web pages using tags to define the structure and presentation of documents. It serves as the foundation of web pages, and understanding its structure is crucial for web scraping. Markup describes presentation as well as data, so extracted text usually needs cleaning.

### HTML document tree · `Web & APIs`

The structure imposed on every HTML document, which is like a tree that may contain strings and other tags. Tags act as nodes, and because a tag can contain strings and further tags, those contents become its children. Navigating the tree from a parent to the right child is most of the work of extracting a table.

### HTML tables · `Web & APIs`

A structured grid format for displaying data on a web page, built from `<table>`, `<tr>`, `<th>` and `<td>` elements. The `<table>` tag defines the table, each row is defined with `<tr>`, the first row often uses the header tag `<th>`, and each cell is a `<td>`. Rows and cells nest, so a table converts into a data frame.

### HTML tags and attributes · `Web & APIs`

A specific code enclosed in angle brackets that defines an element within a document, consisting of an opening (start) tag and a closing (end) tag. Tags have names, such as `<a>` for an anchor tag, and may carry attributes with a name and value that add information. Attributes are often the only reliable way to select the element you want.

### HTTP · `Web & APIs`

The HyperText Transfer Protocol, which transfers data including web pages and resources between a client such as a web browser and a server on the World Wide Web. It is the foundation of data communication on the web, so every API call and every scrape is an HTTP exchange. Four verbs plus two message shapes cover nearly the whole vocabulary.

### HTTP message (request and response) · `Web & APIs`

The unit of exchange in HTTP, where a request carries instructions for operations and typically includes a JSON file, and the response returned by a web service includes information such as the type of resource and its length. Sending a request and receiving a response is how a REST API functions. The status code tells you whether the operation succeeded.

### HTTP methods · `Web & APIs`

The four standard verbs of HTTP, each carrying a different intent. `GET` is one of the popular methods of requesting information, `POST` submits data to be processed, `PUT` replaces the target resource, and `DELETE` removes it. `GET` places its parameters in the URL and is safe to repeat, whereas the others send a body and change server state.

### Hue · `Tool`

In charting, the variable mapped to colour, which splits one series into per-category colours and adds a third dimension to a two-variable plot; it is passed as `hue=` in Seaborn and Plotly Express. Separately, Hue is the name of an open-source web interface for querying and visualising large datasets held in Apache Hadoop.

### Hugging Face · `Cloud Platform`

A hub and open-source ecosystem around pretrained models and datasets, best known for the `transformers` library and for hosting model cards, weights and demo spaces. It is where most open-weight models are published and compared.

### Hyperparameter · `Machine Learning`

A setting chosen before training that the learning algorithm does not fit from data — tree depth, learning rate, regularisation strength, number of neighbours. It is tuned on validation data because tuning it on the test set silently turns the test set into training data.

### Hyperparameter tuning · `MLOps`

Searching the settings a model cannot learn from data — tree depth, learning rate, regularisation strength, kernel parameters — by training many configurations and comparing validation scores. Grid search is exhaustive, random search covers wide ranges efficiently, and Bayesian search spends trials where the evidence points.

---

## I

*30 terms*

### IBM Adversarial Robustness 360 Toolbox · `Cloud Platform`

A free and open-source library for measuring a model's robustness and vulnerability to adversarial attacks, and for improving that robustness and detecting adversarial examples. It turns an abstract security concern into measurable metrics and mitigations. It complements, rather than replaces, testing against attacks specific to your own domain.

### IBM AI Explainability 360 · `Cloud Platform`

An open-source toolkit for explaining model behaviour and decisions, offering methods for measuring explainability plus algorithms that generate explanations and visualisations. It supplies a range of explanation styles rather than a single technique, so the choice depends on the audience and the model. Explanations describe the model's behaviour, which is not the same as its causal reasoning.

### IBM AI Fairness 360 · `Cloud Platform`

An open-source toolkit for detecting and mitigating bias in machine-learning models, providing bias metrics across protected attributes and pre-, in- and post-processing mitigation algorithms. It makes fairness measurable at three different points in the pipeline. A metric improves only what it measures, so choosing the metric is itself the substantive decision.

### IBM Cloud · `Cloud Platform`

IBM's cloud platform, hosting the managed services that made up the classic IBM data-science stack: Watson Studio, Db2 on Cloud, Cloudant and Watson Machine Learning.

### IBM Data Refinery · `Cloud Platform`

A data-integration and visualisation component of IBM Watson Studio that defines and executes data-integration processes in a spreadsheet-style interface. It amounts to self-service ETL for analysts who do not write pipeline code. Spreadsheet-style transformation scales less comfortably than code once the process must be scheduled or versioned.

### IBM Watson Machine Learning · `Cloud Platform`

IBM's cloud service for model building and deployment, listed under cloud model building alongside Google AI Platform Training and under cloud model deployment alongside SPSS Collaboration and Deployment Services. It moves a model from a notebook into a served endpoint. Deployment brings monitoring, scaling and credential concerns that training alone does not raise.

### IBM Watson OpenScale · `Cloud Platform`

IBM's model-monitoring and assessment service, covering the complete development life cycle and monitoring the quality and fairness of deployed models rather than only server health. It tracks whether predictions stay trustworthy after deployment, when data drift erodes them. Monitoring accuracy needs ground-truth labels, which often arrive late.

### IBM Watson Studio · `Cloud Platform`

IBM's integrated data-science platform, available in cloud and Desktop forms, combining Jupyter Notebooks with graphical tools, and whose Data Refinery component performs spreadsheet-style data integration. It gives a team visual and code-based routes into the same project. The graphical layer is convenient for exploration but harder to place under version control than a notebook.

### IBM watsonx · `Cloud Platform`

IBM's AI and data platform, split into watsonx.ai for building and tuning foundation models, watsonx.data for an open lakehouse and watsonx.governance for managing model risk. It is IBM's answer to the combined data-and-AI platform category.

### Idempotency · `Data Architecture`

The property that running an operation twice leaves the same result as running it once. It is what makes retries safe, and pipelines achieve it by writing to a partition that is replaced wholesale, by merging on a key, or by deduplicating on an event identifier.

### iloc · `Python`

A pandas index-based selecting method that requires an integer index to select a specific row or column, written `iloc[row_index, column_index]`, and that does not include the last element of the range passed to it. It gives positional access with ordinary Python slice semantics, which suits data whose index is not meaningful. Confusing it with label-based selection causes off-by-one errors.

### Immutable · `Python`

Objects of built-in data types such as `int`, `float`, `bool`, `string`, `Unicode` and `tuple`, which cannot be changed after they are created. Immutability explains why `my_string.upper()` appears to do nothing unless its result is assigned, and why tuples can serve as dictionary keys while lists cannot. Operations evaluate to a new object rather than modifying the original.

### Imputation · `Machine Learning`

Replacing missing values with a substitute, most commonly the mean of the column, computed as `AverageValue = df['attribute_name'].astype(<data_type>).mean(axis=0)` and applied with `df['attribute_name'].replace(np.nan, AverageValue, inplace=True)`. It is the default for a continuous variable because it preserves the column mean by construction, needs no extra data and takes one line. It also shrinks the variance and biases every correlation toward zero.

### IN · `SQL`

A SQL operator allowing a set of values in a `WHERE` clause, so that `WHERE country = 'AU' OR country = 'BR'` becomes `WHERE country IN ('AU', 'BR')`. It replaces an `OR` chain, which reads better as the set grows, and it is the shape a sub-query slots into as `IN (SELECT ...)`. NULLs never match.

### In-context learning · `Generative AI`

A model's ability to pick up a task from instructions and examples inside the prompt without any weight update. It is why few-shot prompting works at all, and it is bounded by the context window and by how well the examples represent the real cases.

### Indentation and indices · `Python`

Indentation is the use of whitespace at the beginning of a line to signify the structure and scope of code blocks such as loops and functions. Indices give the position of elements in a sequence such as a string, list or tuple, starting with `0`. Indentation is syntax rather than style, and mixing tabs with spaces raises an error.

### Indexing · `Python`

The operation that accesses a character at a specific index, written `[i]` and counted from zero, as in `my_string = "Hello"` followed by `char = my_string[0]`, which yields `'H'`. `0` is the first character and `len(s) - 1` the last, while an out-of-range index raises `IndexError`.

### Infrastructure as a Service (IaaS) · `Cloud`

A cloud service model providing access to computing infrastructure, namely servers, storage and networking, without the user managing the physical layer. It supplies raw machines rather than a managed runtime, leaving patching and scaling to the customer. The control it grants is also the operational burden it transfers.

### INSERT INTO … VALUES · `SQL`

The SQL statement that adds a row to a table, written with a named column list such as `INSERT INTO Instructor ("lastname", "city") VALUES ("anaya", "gdl");` or across multiple rows at once. The column list frees the statement from the table's column order and lets unlisted columns take their default, `NULL` when none is declared.

### install.packages() · `R`

The R function that installs packages from a repository, CRAN by default, serving as R's package-management step and analogous to `pip install` in Python. It is commonly paired with `installed.packages()` to report what is already present. Installation writes to a library path shared by the whole environment, so reproducibility depends on recording versions.

### Instance · `Python`

An individual object created from a class, produced by calling the class followed by parentheses. Each object is independent and has its own set of attributes and methods, so two instances of one class can hold entirely different state. State set on one instance never appears on another unless it was defined on the class itself.

### Instruction tuning · `Generative AI`

Fine-tuning a pretrained model on paired instructions and desired responses so it follows directions rather than merely continuing text. It is the step that turns a raw language model into something usable as an assistant.

### Integer · `Python`

A whole number: zero, a positive natural number such as `1, 2, 3`, or a negative integer written with a minus sign, and unbounded in Python. It is the type of every count, index and identifier, and the type that `//` and `%` return for integer inputs. Being unbounded, it grows silently rather than overflowing.

### Integrated Development Environment (IDE) · `Tool`

A software application that provides a workspace plus the tools to develop, implement, execute, test and deploy source code, typically an editor, language services and a debugger, often with version control. It shortens the edit-run-inspect loop that dominates day-to-day work. A plain editor remains adequate for exploration, so the heavier tooling earns its cost on larger projects.

### Interactive shell / REPL session · `Tool`

The environment in which code is typed and executed line by line with immediate feedback, announced by an interpreter banner such as `Python 3.13.11` and driven by a `>>>` prompt, with values echoed and tracebacks printed as they occur. Variables live only as long as the session, so anything worth keeping must be written to a file.

### Interquartile range · `Statistics`

The distance between the 25th and 75th percentiles, covering the middle half of the data. It is the spread measure that pairs with the median because, like it, the IQR depends on rank rather than magnitude and so resists outliers.

### Intersection · `Statistics`

The operation producing a new set containing only the elements present in both input sets, written with the `&` operator, a character standing for the word and, or by calling `.intersection()`. The logic of in both underlies joins, overlaps and filters, and the operator expresses it in one step instead of a loop. It applies to sets.

### ipywidgets · `Library`

The Jupyter widget framework that adds controls such as sliders, dropdowns and buttons to a notebook, synchronising Python widget objects with JavaScript counterparts. It turns a notebook cell into a small interactive application, named among the libraries that a browser-based Jupyter environment supports. Widget state lives in the kernel, so a restarted kernel loses it.

### Iteration · `Methodology`

A single cycle or repetition of a process involving refinement based on feedback or new information. It is the mechanism behind a cyclical methodology's claim, and the reason model evaluation counts as an ongoing activity rather than a one-time gate. Each iteration should change something specific, or the loop becomes repetition.

### Iterative Assessment · `Methodology`

The observation that iterations refine both problem definition and collection methods, meaning assessment can rewrite the earliest stages of a project as well as the later ones. A data collection choice made first may be revised once the problem is better understood, so the loop is not confined to the end. Treating the sequence as strictly linear hides this feedback.

---

## J

*12 terms*

### Java · `Language`

A general-purpose, tried-and-tested object-oriented language designed to be fast and scalable, compiled to bytecode that runs on the Java Virtual Machine. Its maturity and performance made it the enterprise and big-data platform language. Verbosity relative to scripting languages is the usual complaint.

### Java Virtual Machine (JVM) · `Programming`

The runtime on which Java bytecode executes, and therefore the reason Scala is interoperable with Java and a whole family of big-data tools shares one platform. Because several languages compile to the same bytecode, they can call each other's libraries directly. Startup and memory tuning are the practical costs of the shared runtime.

### Java-ML · `Library`

A single-process machine-learning library built with Java, listed alongside Weka among Java machine-learning tools. It runs in one process rather than distributing work across a cluster, which suits smaller datasets and embedding. Modern deep learning work rarely happens here.

### JavaScript · `Language`

The core technology of the world wide web, a general-purpose language extended beyond the browser by Node.js, and explicitly not related to Java despite the name. Its machine-learning surface includes TensorFlow.js, brain.js and machinelearn.js. Browser execution makes it strong for interactive visualisation and weaker for heavy model training.

### Joins · `SQL`

The operation combining data from two tables, and the reason the relational model exists. An implicit inner join is written `SELECT * FROM EMPLOYEES, JOBS WHERE EMPLOYEES.JOB_ID = JOBS.JOB_IDENT;`, and an explicit one as `SELECT * FROM JOBS J INNER JOIN EMPLOYEES E ON E.JOB_ID = J.JOB_IDENT`. Only matching rows survive, so a key present on one side alone disappears.

### JSON · `Data Engineering`

JavaScript Object Notation, a lightweight data interchange format that stores structured data in human-readable text, commonly used for configuration, data exchange and web APIs. It is the payload format of nearly every REST response, and `r.json()` is the call that turns the response text into Python dictionaries and lists. It has no comment syntax and no schema of its own.

### Julia · `Language`

A language designed at MIT for high-performance numerical analysis and computational science, compiled to run as fast as C or Fortran while developing like Python or R. It can call C, Go, Java, MATLAB, R, Fortran and Python libraries, which lets it reuse existing numerical code. Its ecosystem is smaller than Python's, so library gaps are the usual obstacle.

### JuliaDB · `Library`

JuliaDB is a Julia package for working with large persistent datasets, built around an out-of-core columnar table type that can exceed available memory. It serves as Julia's data-science surface for tabular data, complementing the language's general array and statistics stack.

### Jupyter Notebook · `Tool`

Jupyter Notebook is a computational notebook document, stored as an `.ipynb` file, that interleaves executable code cells, narrative text and stored output in one place. It supports dozens of programming languages and executes cells against a persistent kernel, so results depend on the order in which cells were run.

### JupyterHub · `Tool`

JupyterHub is the multi-user server that extends Jupyter Notebook and JupyterLab capabilities to an organisation: one deployment serves many isolated single-user servers, each with its own environment. It adds central authentication and resource control, so accounts and compute are managed from a single point.

### JupyterLab · `Tool`

JupyterLab is an open-source, web-based application built on Jupyter Notebook, offering a next-generation tabbed workspace for code, visualisations, text and equations side by side. It inherits the pre-installed scientific stack of distributions such as Anaconda, so data-science libraries are available without extra setup.

### JupyterLite · `Tool`

JupyterLite is a lightweight tool assembled from JupyterLab components that executes entirely in the browser and needs no dedicated Jupyter server. Because the kernel runs client-side, it supports only browser-capable libraries such as Altair, Plotly and ipywidgets, and storage is limited to the page.

---

## K

*10 terms*

### Keras · `Library`

Keras is a high-level Python deep-learning library for building neural networks in a few lines, abstracting away the low-level tensor operations. It is now TensorFlow's official high-level API, imported as `tf.keras`, which makes it the shortest path from a layer description to a trained model.

### Kernel · `Tool`

A kernel is the computational engine that executes the code inside a notebook, running as a persistent process that holds variables and imports between cells. That persistence is why notebook results depend on execution order, and why restarting the kernel is the reliable way to reproduce a notebook from scratch.

### k-fold cross-validation · `Machine Learning`

Splitting the data into k folds, training on k−1 and validating on the held-out fold, and rotating, so every row is validated exactly once. It uses the data more efficiently than a single split and reports a spread across folds, which is the honest measure of stability.

### Kibana · `Tool`

Kibana is an open-source data-visualisation tool used with Elasticsearch to analyse and visualise large datasets through a web interface, with dashboards, charts and search built on the indexed data. It is limited to Elasticsearch as its data provider, so it is not a general-purpose charting library.

### K-means · `Machine Learning`

K-means is an iterative, centroid-based clustering algorithm that partitions a dataset into similar groups based on the distance between their centroids, categorising points by a mathematical distance measure from the cluster centre. It performs poorly on imbalanced clusters and assumes that clusters are convex.

### K-nearest neighbours (KNN) · `Machine Learning`

K-nearest neighbours is a supervised machine learning algorithm that uses labelled points to learn how to label other points, assigning labels based on the closest labelled data points. It supports both classification and regression, and because it stores the training set rather than fitting coefficients, prediction cost grows with the data.

### KNIME · `Cloud Platform`

An open-source visual analytics platform where analysis and machine learning are assembled as a workflow of connected nodes over a spreadsheet-like table model. It is code-optional rather than code-free, since scripting nodes can be dropped in.

### KPI (key performance indicator) · `Analytics & BI`

A metric chosen in advance as the measure of whether an objective is being met, with an owner, a target and a definition everyone accepts. The discipline is in the definition: if two teams compute revenue differently, neither number is a KPI.

### Kubeflow · `Cloud Platform`

Kubeflow is an open-source machine-learning toolkit for running data-science pipelines on Kubernetes, wiring each pipeline step into a containerised workflow. It covers distributed training, model serving and hyperparameter tuning, which makes Kubernetes the scheduling substrate for the whole model lifecycle.

### Kubernetes · `Cloud Platform`

Kubernetes is an open-source container-orchestration platform that launches, scales and manages containerised applications automatically across many hosts. Its autoscaling, self-healing and load balancing are what let a deployed service survive node failure and traffic spikes without manual intervention.

---

## L

*25 terms*

### Lambda architecture · `Data Architecture`

An architecture that runs a batch layer for accuracy and a speed layer for low latency over the same input, with a serving layer merging both. It works, and it costs two implementations of every piece of logic — which is why unified engines that handle batch and streaming in one API displaced it.

### LangChain · `Generative AI`

A framework for composing applications around language models: prompt templates, chains, tool and function calling, memory, document loaders, retrievers and agents. It standardises the plumbing between a model and everything it needs to touch, at the cost of an abstraction layer to learn.

### Large language model (LLM) · `Generative AI`

A neural network with billions of parameters trained on large text corpora to predict the next token, which is enough to make it summarise, translate, write code and answer questions. Its competence comes from scale and from pretraining breadth, not from any task-specific design, and its knowledge is frozen at its training cut-off.

### Lasso regression · `Machine Learning`

A linear model with an L1 penalty on the coefficient sizes, which shrinks the least useful coefficients exactly to zero and therefore performs feature selection as it fits. It is the tool of choice when many predictors are present and only a few are expected to matter.

### lattice · `R`

lattice is one of R's four data-visualisation packages, aimed at complex multi-variable datasets. Its formula interface takes conditioning variables and produces trellis panels, giving one small multiple per level so that interactions between variables become visible rather than being flattened into a single chart.

### leaflet · `Library`

leaflet is one of R's four data-visualisation packages, used for interactive plots. It wraps the Leaflet JavaScript library to render tiled maps with markers and polygons, so geographic point or area data can be explored by panning and zooming inside a knitted document or application.

### Library, package and module · `Programming`

A library is reusable code containing built-in modules whose functionality can be used directly, a package is the unit by which that code is distributed and installed, and a module is the file or namespace you import. In Python the three collapse into one import statement, but only packages are installed and only modules appear in `import` lines.

### LIKE · `SQL`

LIKE is SQL's pattern-matching operator for filtering text, where `%` stands for any run of characters: `where DESCRIPTION LIKE '%minor'` matches values ending in minor, while `where PRIMARY_TYPE LIKE 'kidn%'` matches values beginning with kidn. The precedence trap is that `WHERE a LIKE 'x%' OR '%x'` parses as `(a LIKE 'x%') OR ('%x')`, so the second pattern is never applied.

### LIMIT · `SQL`

LIMIT bounds a result set: `LIMIT n` truncates the output to n rows after `ORDER BY` has run, and `OFFSET m` skips the first m rows. Because the offset is zero-based, retrieving 15 rows starting from row 11 is `SELECT * FROM FilmLocations LIMIT 15 OFFSET 10`, the standard way to page an exploratory query.

### Line plot · `Visualization`

A line plot draws values in sequence and joins consecutive points with straight segments, showing trend or change along an ordered axis such as time. pandas ships a built-in implementation of Matplotlib, so a Series or DataFrame produces one directly through `df.plot()`, and it is the default way a trendline is read off a cleaned dataset.

### Linear regression · `Machine Learning`

Linear regression fits a straight-line relationship that predicts a numeric target from one or more predictors, choosing the line that minimises squared error. In Python it is three lines: `from sklearn.linear_model import LinearRegression`, `lm = LinearRegression()`, `lm.fit(X, Y)`, after which `lm.coef_` and `lm.intercept_` hold the fitted line.

### linspace · `Python`

`numpy.linspace(start, stop, num)` generates an array of evenly spaced values across an interval, where `start` is the start of the interval range, `stop` the end, and `num` the number of samples to generate. It builds an x-axis with a fixed number of points spanning the range, inclusive of the endpoint.

### List methods · `Python`

List methods are the operations bound to Python list objects: `append()` adds an element to the end, `extend()` takes an iterable and appends each of its elements, `insert()` inserts an element at a position, `remove()` removes the first occurrence of a specified value, and `pop()` removes and returns the element at a specified index.

### Lists · `Python`

A list is an ordered collection of data items, separated by commas and enclosed in square brackets, that can hold elements of different types and is mutable. Every intermediate result in a data pipeline, from parsed rows to feature names to tokens from `split()`, is a list, and mutability is what makes accumulation into one cheap.

### LlamaIndex · `Generative AI`

A framework focused on connecting language models to private data: loading and chunking documents, building indexes, retrieving relevant context and synthesising answers with citations. It is the retrieval half of a RAG application made into a library.

### LLM-as-judge · `Generative AI`

Using a language model to score another model's output against a rubric, so evaluation can scale beyond what human review covers. It is the standard way to grade open-ended generation, where exact-match metrics are useless, and it is good enough to rank two systems while still biased toward longer, more confident and self-similar answers. Treat it as a measurement with its own error rate: calibrate it against human labels on a sample before trusting it on everything.

### loc · `Python`

`loc` is a label-based data-selecting method, meaning the name of the row or column is passed rather than a numeric position: `loc[row_label, column_label]`. It is inclusive of the last element of the range passed to it, which is the key difference from positional slicing and a frequent source of off-by-one confusion.

### Log loss · `Machine Learning`

Also called binary cross-entropy, the loss that scores predicted probabilities by how far they sit from the true labels, penalising confident mistakes most heavily. It is the objective logistic regression minimises, and it is preferred to accuracy when the calibrated probability matters and not only the final class.

### Logic operators (and, or, not) · `Python`

Python's logic operators `and`, `or` and `not` perform logical operations on Boolean values, with `and` true only when both operands are true, `or` true when at least one is, and `not` negating a single value. They are also called Boolean logic operators, and they are the glue of every compound filter condition.

### Logistic regression · `Machine Learning`

Logistic regression is a statistical modelling technique that predicts the probability of an observation belonging to one or two classes, such as true or false. The predicted probability is converted into a class decision, which makes the method a classification algorithm even though its output is a continuous, interpretable probability score.

### Looker · `Analytics & BI`

Google's BI platform built around LookML, a modelling language that defines dimensions and measures centrally so every dashboard and query uses one governed definition. That central model is its distinguishing feature, and it is why it appeals to organisations fighting inconsistent metrics.

### Looker Studio · `Analytics & BI`

Google's free browser-based reporting tool, originally Data Studio, for assembling charts over BigQuery, Sheets and other connectors into shareable reports. It is quick for a small report and limited for governed, high-volume analysis.

### Loops · `Python`

Loops are Python constructs for repeating a block of code, enabling the execution of the same code multiple times, and they automate repetitive tasks while iterating over data structures such as lists or dictionaries. `for` walks an existing sequence a known number of times, whereas `while` repeats until a condition stops holding.

### LoRA (low-rank adaptation) · `Generative AI`

A parameter-efficient fine-tuning method that freezes the original weights and trains small low-rank matrices alongside them, cutting the memory and cost of adaptation dramatically. The adapters are portable, so one base model can serve several specialisations.

### Loss function · `Machine Learning`

The function training minimises, which encodes what counts as a mistake — squared error for regression, log loss or cross-entropy for classification, a margin-based loss for support vector machines. Choosing it is a statement about which errors matter, not a technical formality.

---

## M

*54 terms*

### Machine Learning · `Machine Learning`

Machine learning is a subset of artificial intelligence that uses computer algorithms to analyse data and make intelligent decisions based on what has been learned, without being explicitly programmed. Its three broad settings are supervised, unsupervised and reinforcement learning, distinguished by whether labels, structure or reward signals drive the learning.

### main / master branch · `Tool`

The main (or master) branch is the canonical branch of a project, holding the official version of the work and acting as the integration target for every other branch. Naming it `main` is the modern default, and keeping it deployable is what makes branching and merging safe for a team.

### Majority-class baseline · `Machine Learning`

The majority-class baseline is the accuracy a trivial model reaches by always predicting the most frequent class, read straight off a target's `value_counts()`. It is the reference every model must beat: `84 %` accuracy against a `76.3 %` baseline is a gain of `7.7` points, and `51 %` rain recall shows what that headline is made of.

### Map Process · `Data Engineering`

The map process is the first step of Hadoop's MapReduce model, in which data is processed in parallel on individual cluster nodes. Each call takes a key-value pair and emits a list of intermediate pairs, `map(k1, v1) → list(k2, v2)`, typically performing a transformation that needs no knowledge of the other records.

### MapReduce · `Data Engineering`

MapReduce is Hadoop's batch programming model, running a map phase, a shuffle and sort phase and a reduce phase over key-value pairs. Intermediate results are written to disk between stages, which makes the model fault-tolerant on large clusters but adds I/O latency compared with in-memory engines.

### Market Basket Analysis · `Machine Learning`

Market basket analysis examines which goods tend to be bought together, turning transaction records into marketing insight such as product placement and recommendation rules. The resulting rules are scored by support, confidence and lift, and the frequent itemsets underneath them are mined with algorithms such as Apriori or FP-Growth.

### Master data management (MDM) · `Data Governance`

Maintaining the single authoritative record of core business entities — customer, product, supplier, employee — and reconciling the duplicates and disagreements that accumulate across systems. It is the hardest governance problem because it requires agreement between business units, not merely a tool.

### Materialized view · `Data Architecture`

A view whose result is physically stored and refreshed, so a repeated expensive aggregation is read rather than recomputed. It trades storage and freshness for speed, and the design question is always how stale the answer may be.

### Mathematical computing · `Concept`

Mathematical computing is the use of computers to calculate, simulate and model mathematical problems, spanning numeric methods such as floating-point arithmetic, linear algebra, optimisation and Monte Carlo simulation, as well as symbolic methods that manipulate expressions exactly. It underpins every downstream statistical and machine-learning routine.

### Matplotlib · `Visualization`

Matplotlib is the most popular Python visualisation library for plots and graphs, and the base layer that other Python charting tools either wrap or are compared against. Its two-part model separates the `Figure` canvas from the `Axes` on which data is drawn, with the `pyplot` interface providing the imperative shortcut.

### Matrices · `Statistics`

A matrix is a rectangular, tabular array of numbers used throughout mathematics, statistics and computer science, and it is the native data structure of statistical computing. A modelling matrix conventionally has shape `(n_samples, n_features)`, so each row is an observation and each column a variable fed to the algorithm.

### Mean · `Statistics`

The mean is the average value of a set of numbers, computed as `x̄ = Σxᵢ / n`. It is the least robust of the common summary statistics because a single extreme value moves it, and its divergence from the median is the quickest signal that a distribution is skewed.

### Measured Service · `Cloud`

Measured service is the cloud property under which resources are billed on actual usage, with utilisation transparently monitored, measured and reported to the customer. It is what turns infrastructure spending into a variable, metered cost that can be attributed and optimised per workload.

### Medallion architecture · `Data Architecture`

A layered organisation of a lakehouse as bronze (raw ingested data), silver (cleansed and conformed) and gold (aggregated, business-ready) tables. Each layer is a checkpoint that can be rebuilt from the one before, which makes debugging a bad number a matter of finding the layer where it went wrong.

### Median · `Statistics`

The median is the middle value in a sorted dataset, the point that splits the data into two equal halves once the observations are ordered. It is the mean's robust counterpart, because it depends on rank rather than magnitude, so outliers barely move it and the mean-median gap becomes a diagnostic for skew.

### Merge · `Tool`

A merge combines the changes of one branch into another, producing a fast-forward when the target branch has not diverged and otherwise a merge commit with two parents. When both branches touched the same lines the merge stops, and the conflict must be resolved by hand before the history continues.

### Message queue · `Data Engineering`

A buffer that holds messages between producers and consumers so that a slow or failed consumer does not lose data or stall the producer. It provides decoupling and back-pressure; a log-based broker such as Kafka adds replay and multiple independent readers.

### Metabase · `Analytics & BI`

An open-source BI tool that lets non-technical users ask questions of a database through a point-and-click interface and save the result as a chart or dashboard. Its value is a low barrier to the first question, with SQL available when the visual builder runs out.

### Metadata · `Data Governance`

Data about data: schemas, types, keys, owners, descriptions, freshness, access rules and lineage. Technical metadata makes systems work; business metadata — what a field means and who owns it — is what makes data usable by people who did not build it.

### Methodology · `Methodology`

Methodology is a system of methods, a guideline for decision-making during the scientific process rather than a single technique. Its three activities are performing data collection, creating measurement strategies and comparing data analysis methods, which together decide what evidence is trustworthy before any modelling begins.

### Methods (instance methods) · `Python`

Instance methods are functions defined within a class that operate on the instance's own data, the instance attributes, and can perform actions specific to instances. Methods are what interact with and change data attributes, and the `self` parameter is why one definition can act on any instance passed to it.

### Microsoft Azure · `Cloud Platform`

Microsoft's cloud platform, offering Azure Machine Learning, Synapse Analytics, Microsoft Fabric, Blob Storage and a managed Databricks service. Its advantage inside enterprises is usually integration with existing Microsoft identity, tooling and licensing.

### Microsoft Fabric · `Cloud Platform`

Microsoft's software-as-a-service analytics platform built on OneLake, bringing Power BI, Data Factory, Synapse-style warehouses and Spark notebooks under one capacity-based licence. Because the services share a single storage layer, a table written by one workload is immediately queryable by the others.

### Microsoft Power BI · `Analytics & BI`

Microsoft's BI platform, combining the Power Query transformation engine, a tabular model with the DAX calculation language, and published dashboards. It is the default where an organisation already lives in Excel, Teams and Azure.

### Milvus · `Generative AI`

An open-source, distributed vector database designed for billion-scale similarity search, with several index types, scalar filtering and separation of storage from compute. It is the self-hosted counterpart to managed vector services.

### Missing Values · `Data Engineering`

Missing values are entries that are absent or unknown in a dataset, and they require careful handling during data preparation because most algorithms cannot consume them directly. Treating them as a decision rather than a cleanup means choosing deliberately between dropping rows, imputing a value or flagging the gap as its own signal.

### Mixture of experts (MoE) · `Generative AI`

An architecture in which a router sends each token to a small subset of specialised sub-networks, called experts, rather than running the whole network. Total parameter count can be enormous while compute per token stays modest, which is why several frontier models are built this way. The trap is memory: every expert has to be resident even though few are used on any given token, so MoE trades compute for VRAM and makes serving harder.

### MLeap · `Library`

MLeap is an open-source library for serialising and deserialising learning models into a cross-platform file format. It exports models from Spark, scikit-learn and TensorFlow so they can be served with high throughput and low latency outside the training environment, decoupling the training stack from the serving stack.

### MLflow · `MLOps`

An open-source platform for the machine-learning lifecycle, with four components: tracking for parameters, metrics and artifacts, projects for reproducible runs, models for a standard packaging format, and a registry for staging and promoting versions. It is the de facto default for experiment tracking and works with any framework.

### MLlib · `Library`

MLlib is Apache Spark's machine-learning library, providing distributed implementations of the standard algorithm families that operate on DataFrames and RDDs. It is what makes Spark a modelling platform as well as an execution engine, letting training scale across a cluster without moving data out of it.

### MLOps · `MLOps`

The discipline of running machine-learning systems in production: versioning data and models, automating training and deployment, monitoring live performance and closing the loop back to retraining. It exists because a model is not a deliverable but a running service that decays as the world it was trained on changes.

### Model Asset eXchange (MAX) · `Cloud Platform`

The Model Asset eXchange is IBM's open-source curated repository of deep-learning models for text, image, audio and video. It holds deployable models that run as a microservice locally or in the cloud on Docker or Kubernetes, alongside trainable models that can be fine-tuned on new data.

### Model Building · `Machine Learning`

Model building is the process of developing predictive models to gain insights and support decisions, the core activity of the modelling stage. It is deliberate construction guided by the question being asked, not a search for the highest score on whatever data happens to be at hand.

### Model Calibration · `Machine Learning`

Adjusting a model so its outputs match reality at the level the problem needs, using the training data as the gauge and the business requirement as the target rather than the training loss alone. A model can rank well and still be miscalibrated, which matters whenever the probability itself is used.

### Model card · `MLOps`

A short document published with a model recording its intended use, training data, evaluation results, limitations and known biases. It is the minimum transparency artefact for anyone deciding whether to trust the model with a real decision.

### Model deployment · `MLOps`

Making a trained model available for use: packaging it with its preprocessing, exposing it behind an interface, and putting it under monitoring and version control. Deployment is the act; the runtime shape it produces — endpoint, batch job or embedded library — is the serving pattern, and the hard part is guaranteeing that scoring-time transformations match training exactly.

### Model Evaluation · `Machine Learning`

Model evaluation assesses the quality and relevance of a model before deployment, carried out iteratively and alongside model building rather than once at the end. Quality comes from the diagnostic measures, while relevance asks whether the model answers the initial business question that motivated the work.

### Model lifecycle · `MLOps`

The model lifecycle is the five-step path a deployed model follows: prepare data, build the model, train it, deploy it and use it. Four inputs are required throughout, namely data, model code, compute resources and domain expertise, and without any one of them the later steps cannot be completed.

### Model monitoring · `MLOps`

Continuously measuring a deployed model's inputs, outputs and — when labels arrive — its accuracy, with alerting on drift, degradation and broken assumptions. Monitoring inputs against a training baseline is what catches silent failure while predictions still look plausible.

### Model Refinement · `Machine Learning`

Model refinement adjusts and improves the data-science model based on user feedback and observed real-world performance. It is the output of the feedback stage, and it is what makes the lifecycle a cycle that improves rather than a one-off pipeline that merely runs.

### Model registry · `MLOps`

A versioned catalogue of trained models with stages such as staging, production and archived, plus the lineage of the run that produced each one. It is what makes promotion and rollback of a model an operational act rather than a file copy.

### Model selection · `Machine Learning`

Choosing among candidate algorithms and configurations by comparing their cross-validated performance, complexity and interpretability rather than their score alone. The usual tie-breaker is the simpler model, since it is cheaper to run, easier to explain and less likely to have been tuned into the validation set.

### Model serving · `MLOps`

Model serving is the deployment packaging pattern in which a pretrained model is bundled with input preprocessing, output postprocessing and a public API, then run as a container. The container is the deployment unit, so the same package can be started locally or on a cluster without rewriting the inference code.

### Model training · `Machine Learning`

Model training is the process by which a model learns the patterns in data: an objective is defined, parameters are initialised, and an optimiser reduces the loss on the training data. Held-out data is used at the same time to detect overfitting, since training loss alone always improves as capacity grows.

### Model zoo · `Machine Learning`

A model zoo is a public repository of ready-trained models provided by a framework, with TensorFlow, PyTorch, Keras and ONNX zoos among the well-known examples. Because pretrained weights are freely downloadable, loading an existing model and fine-tuning it has become the normal starting point rather than training from scratch.

### ModelDB · `MLOps`

ModelDB is an open-source platform for managing machine-learning models and experiments. It provides experiment tracking, model versioning and team collaboration, giving a shared record of what was trained, with which settings, and which artefact resulted.

### MongoDB · `Database`

MongoDB is a document-oriented NoSQL database that stores flexible JSON documents rather than rows in fixed tables. It offers scalability, high availability and data distribution, which makes it suited to web applications handling large volumes of unstructured data whose shape changes over time.

### MSE (mean squared error) · `Statistics`

Mean squared error measures the average of the squares of errors, the difference between the actual value `y` and the predicted value `ŷ`. It is computed as `from sklearn.metrics import mean_squared_error; mse = mean_squared_error(Y, Yhat)`, and unlike unitless R² it is absolute, expressed in the target's units squared.

### Multiclass classification (one-vs-all, one-vs-one) · `Machine Learning`

Multiclass classification extends a binary classifier to more than two classes using one-versus-all or one-versus-one strategies. One-versus-all trains `k` classifiers against the rest, while one-versus-one trains `k(k−1)/2` pairwise classifiers and votes; on a seven-class problem the one-versus-one setup won by `4.3` points.

### Multimodal model · `Generative AI`

A model that accepts and produces more than one kind of data — text, images, audio — in a shared representation. It removes the need for a separate pipeline per input type, and it is what lets a chart be queried with a sentence.

### Multiple comparisons problem · `Statistics`

The inflation of false positives that occurs when many hypotheses are tested at the same significance level, since five percent of twenty independent tests will appear significant by chance. Corrections such as Bonferroni or false-discovery-rate control, or a pre-registered primary hypothesis, are the standard defences.

### Multiple linear regression · `Machine Learning`

Multiple linear regression uses the same estimator with more columns: `Z = df[['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']]` followed by `lm.fit(Z, df['price'])`. The fitted intercept was `-15806.62462632922` with coefficients `array([53.49574423, 4.70770099, 81.53026382, 36.05748882])`, one per predictor in the order of `Z`'s columns; four predictors explained `0.8094` of price variance where `highway-mpg` alone explained `0.4966`.

### Mutable · `Python`

Mutable objects in Python are objects whose values can be changed after they are created, allowing elements to be added, removed or altered without creating a new object. Mutability decides whether a change is visible through every reference to the object, which is the mechanism behind aliasing bugs and unexpected shared state.

### MySQL · `Database`

MySQL is a popular open-source relational database management system that speaks SQL. It is commonly used for web applications, data warehousing and e-commerce, where its transactional guarantees and mature tooling make it a default choice for structured, relational workloads.

---

## N

*17 terms*

### Naive Bayes · `Machine Learning`

Naive Bayes is a simple probabilistic classifier based on Bayes' theorem that assumes features are conditionally independent given the class. It classifies by `argmax_c P(c) Π P(xᵢ|c)`, computed in log space with smoothing, and the independence assumption is what keeps estimation cheap even when the feature count is large.

### Natural Language Processing (NLP) · `Machine Learning`

Natural language processing is a field of artificial intelligence that enables machines to understand, generate and interact with human language. Its pipeline begins with tokenisation and vectorisation and extends to contextual embeddings and transformers, which now handle most state-of-the-art text tasks.

### Natural Language Toolkit (NLTK) · `Library`

The Natural Language Toolkit is a Python toolkit for natural-language processing that gathers corpora, tokenisers, stemmers, taggers, parsers and classifiers behind one API. It is the classic teaching and prototyping library for text work, with explicit, readable components rather than a single opaque model.

### ndarray (ND array) · `Python`

A NumPy array, or ND array, is similar to a list but usually of a fixed size and holding the same kind of element throughout. Each component, a specific element or value within the multi-dimensional array, is accessed using indexing, and the fixed homogeneous layout is what makes the library a powerful tool for mathematical and scientific computing.

### Negative indexing · `Python`

Negative indexing accesses elements of a sequence such as a list, string or tuple from the end, using negative numbers as indexes. `s[-1]` is the last element and `s[-2]` the one before it, since the index resolves to `len(s) + i`; it replaces the `len(s) - 1` arithmetic that produces off-by-one bugs.

### Nesting · `Python`

Nesting means placing data structures inside one another, so that tuples can include other tuples of complex data types and a list can contain strings, integers and floats as well as further lists. The inner values are reached through indexing, one index per level, which is why deeply nested structures become hard to read.

### NetworkX · `Library`

NetworkX is a Python library for creating, analysing and drawing graphs of nodes and edges. It is used to render the flowchart layer of a data-science submission, installed as version `3.6.1` and exported as PNG images that sit alongside the `.py`, `.db` and `.csv` support files.

### Node.js · `Language`

Node.js is the server-side runtime that let JavaScript extend beyond the browser, making JavaScript machine learning possible outside the page and allowing one language across client and server. Its single-threaded event loop is the caveat: CPU-bound inference blocks it, so heavy model calls must be offloaded to workers or a separate service.

### Node-RED · `Tool`

Node-RED is an open-source visual programming tool for wiring hardware devices, APIs and online services into event-driven message flows by connecting nodes in a browser editor. It is light enough to run on a Raspberry Pi, which makes it a common choice for sensor and IoT prototypes.

### Normalisation · `Data Architecture`

Organising tables so that each fact is stored once, through the normal forms: the first removes repeating groups, the second removes partial dependencies on part of a composite key, and the third removes dependencies between non-key columns. In machine learning the same word means rescaling a variable, usually to 0-1 with min-max scaling, which is a different operation on a different object.

### North star metric · `Analytics & BI`

The single metric a product team treats as the best proxy for the value it delivers to users, chosen so that improving it genuinely means the product is working. It anchors prioritisation, and it must be paired with guardrail metrics that catch harm elsewhere.

### NoSQL Database · `Database`

A NoSQL database belongs to a non-relational family whose members store data in models other than tables, with document-oriented JSON stores as the common example. They offer scalability, availability and data distribution by relaxing fixed schemas and joins, at the cost of weaker transactional guarantees.

### Notebook cell · `Tool`

A notebook cell is the unit of a notebook document, typed as Code for executable statements, Markdown for formatted text or Raw for plain text passed through untouched. Only code cells are sent to the kernel, which is why Markdown cells can hold narrative, headings and equations without affecting execution.

### NULL handling in sorts · `SQL`

NULL handling in sorts determines where rows with missing values land in an ordered result, since a NULL is neither greater nor smaller than any value. An ascending `ORDER BY Average_Student_Attendance LIMIT 5` returned the `None` row first, so the descending version added an explicit `nulls last` clause to keep missing values out of the top of the list.

### Null hypothesis · `Statistics`

The default claim a test tries to discredit, conventionally that there is no effect or no difference. The burden of proof sits with the alternative, and a failure to reject is an inconclusive result rather than evidence that the effect is zero.

### NumPy · `Library`

NumPy is the Python library for arrays and matrices, providing typed n-dimensional arrays with vectorised operations that run in compiled code rather than Python loops. It is the numeric foundation on which Pandas, Matplotlib, scikit-learn and TensorFlow all exchange data, so its array layout and dtype rules leak into every layer above it.

### NumPy indexing and slicing · `Library`

NumPy indexing accesses elements by index, and slicing takes sub-arrays with `[start:end:step]`. The element at the end index is not included in the output, a missing start is taken as `0`, a missing end is taken as the length of the array, and a missing step is taken as `1`.

---

## O

*22 terms*

### Object · `Python`

An object is a fundamental unit in Python that represents a real-world entity or concept, which can be tangible like a car or abstract like a student's grade. It has exactly two characteristics: state, the attributes or data that describe the object, and behaviour, the actions or methods the object can perform.

### Object-oriented programming (OOP) · `Python`

Object-oriented programming is a paradigm centred around objects and classes, and Python is an object-oriented language that uses it. The paradigm is the organising idea behind every library used afterwards: a pandas `DataFrame` is an object with attributes and methods, so reading its API means understanding classes, instances and `self`.

### Observational study · `Statistics`

A study in which the researcher observes and measures without assigning the treatment. It can establish association and, with careful design and adjustment, support causal arguments, but it cannot rule out unmeasured confounding the way randomisation does.

### OLAP · `Data Architecture`

Online analytical processing: the workload of reporting and analysis, made of few but large scans that aggregate many rows. Schemas are denormalised and storage is columnar, because the design goal is scanning speed rather than write throughput.

### OLTP · `Data Architecture`

Online transaction processing: the workload of an operational system, made of many small, concurrent reads and writes that each touch few rows. Schemas are normalised to protect integrity, and the design goal is transaction throughput and latency.

### On-Demand Self-Service · `Cloud`

On-demand self-service is the cloud property by which users provision resources such as processing power, storage and networking through simple interfaces, without any human interaction with the provider. It shifts capacity decisions to the user and makes provisioning a self-service, near-instant operation rather than a procurement process.

### One-hot encoding · `Machine Learning`

One-hot encoding converts a categorical column into numerical form by creating one binary indicator column per category. In pandas it is `pd.get_dummies(df['fuel'])`, or in its fuller form `dummy_variable = pd.get_dummies(df['attribute_name'])` followed by `df = pd.concat([df, dummy_variable], axis=1)` to append the indicators to the original frame.

### OneHotEncoder · `Machine Learning`

`OneHotEncoder` turns categories into indicator columns inside a pipeline, where `drop='first'` is a statistical choice about collinearity and `handle_unknown='ignore'` is an operational one. Without the latter, calling `transform` on data containing a category the encoder never saw raises an error; with it, that category becomes an all-zero row, which lets a fitted pipeline be deployed against new data.

### OneLake · `Cloud Platform`

The single logical data lake that Microsoft Fabric gives every tenant, addressed with the same path syntax as a local file system and storing data in open Delta Parquet format. Shortcuts expose data held in ADLS, S3 or Dataverse without copying it.

### ONNX · `Data Engineering`

The Open Neural Network Exchange, an open format that represents a trained model as a computation graph so it can be exported from one framework and run in another. It is the interchange layer that keeps a model from being locked to the library that trained it.

### open() and the file object · `Python`

`open` is the Python function used to access and manipulate files, allowing reading from or writing to a specified file, and it returns a file object that represents the open file. The object carries a position that persists between calls, which is the reason successive reads continue where the previous one stopped.

### Open data · `Concept`

Open data is data freely available for anyone to access, use, modify and share, including under a public licence. Portals are organised by domain, including government, financial, crime, health, academic and business, and general-purpose collections, giving analysts citable sources without procurement or negotiation.

### Open Source Software · `Concept`

Open source software is software whose source is available under a licence permitting use, modification and distribution. The Open Source Initiative anchors a business-focused definition centred on practical licensing terms, while the Free Software Foundation's definition of free software is value-focused, so the two communities overlap but are not identical.

### Open table format · `Data Architecture`

A specification that adds database behaviour — ACID transactions, schema evolution, time travel, partition pruning — to a directory of Parquet files on object storage. Apache Iceberg, Delta Lake and Apache Hudi are the three implementations, and openness means several engines can read the same table.

### OpenAI API · `Cloud Platform`

The commercial interface to OpenAI's models: chat completions for text generation, embeddings for vector representations, and fine-tuning endpoints. Pricing is per token, which makes token accounting a design constraint rather than an afterthought.

### openpyxl · `Library`

The library pandas uses to read and write Excel workbooks, formerly covered by `xlrd`, and the reason a `read_excel` call can fail with a missing-dependency error. Any engine that can be named explicitly, as in `pd.read_excel(..., engine='openpyxl')`, is part of the environment the pipeline depends on.

### Operators in Python · `Python`

Operators are the symbols used to perform operations on variables and values, and they are the vocabulary of every expression. Knowing which operators return floats, which perform floor division or remainder, and which concatenate instead of adding accounts for much of early fluency, because the same symbol can mean different things for different types.

### Orchestration · `Data Engineering`

Coordinating many dependent tasks so they run in the right order, at the right time, with retries, backfills and alerting when something fails. Orchestrators such as Airflow, Dagster and Prefect encode a pipeline's dependencies as code rather than as a schedule someone remembers.

### ORDER BY · `SQL`

`ORDER BY` sorts a result set, with the form `ORDER BY expr [ASC|DESC]` and multiple keys separated by commas and evaluated left to right; `DESC` reverses the order. The ordinal form `ORDER BY 2` sorts by the second projected column, and because a result set has no inherent order, sorting is also what makes `LIMIT` and `OFFSET` reproducible.

### Ordinary least squares (OLS) · `Statistics`

Ordinary least squares is the fitting method behind simple linear regression, where a single independent variable estimates a dependent variable by minimising mean squared error into a best-fit line. It is simple and easy to understand, its solution was derived independently by the mathematicians Gauss and Legendre in the early 1800s, and its accuracy can be reduced by outliers.

### Outlier · `Statistics`

An observation far from the rest of the distribution, judged by a rule such as more than 1.5 interquartile ranges beyond the quartiles. It may be a data-entry error, a different population, or the most interesting record in the file, and deciding which requires investigation rather than an automatic deletion rule.

### Overfitting and underfitting · `Machine Learning`

Overfitting and underfitting are the two ways a model fails to generalise: an overfitted model learns the training data's noise, so it scores well in-sample and badly out, while an underfitted model is too simple to capture the relationship and scores badly in both. Lower `R^2` means a worse model, and a negative `R^2` signals overfitting.

---

## P

*49 terms*

### Pairwise Correlation · `Statistics`

Pairwise correlation is an analysis that determines the relationships and correlations between different variables, producing one coefficient per pair of columns. Values near `±1` matter most because redundant columns destabilise a linear model and make a tree arbitrary about which of the two it splits on.

### Pandas · `Library`

Pandas is the Python library for data structures and tools that organises data into DataFrames, acting as the layer where cleaning, joining, groupby and reshaping happen. Its mutating API has a sharp edge: `inplace=False` returns a copy and leaves the original untouched, while `inplace=True` mutates the original object and returns nothing.

### pandas.concat() · `Library`

It stacks frames along an axis, most often vertically, building one table out of several. Passing `ignore_index=True` renumbers the result `0..n-1`, while omitting it repeats the original labels. The caller supplies the list, `pd.concat([a, b])`. Alignment happens on columns, so a column present in only one frame is filled with `NaN` rather than dropped.

### pandas.read_sql() · `Library`

A pandas function that runs a SQL query through a DB-API connection and hands the result back as a DataFrame, so query output never has to be parsed by hand. The typical call is `pandas.read_sql(query, connection)`. It is the read half of the pairing, since `to_sql` writes a DataFrame back into a table.

### Parameters and arguments · `Python`

A `def` statement introduces a function definition; the named placeholders inside its parentheses are parameters, and the values supplied at call time are arguments bound to those names. A function can carry multiple parameters. The parameter list is the function's public interface, so settle it before the body matters; positional order drives binding, so a wrong order silently swaps values.

### Parquet · `Data Architecture`

A columnar file format for analytics that stores data by column, compresses it and keeps per-block statistics and a schema, so a reader can skip data it does not need. It is the default file format of lakehouses and the format the open table formats wrap.

### Parsing · `Programming`

Parsing analyses a string of text or a data structure, usually following a set of rules or a grammar, to understand its structure and meaning. It turns raw characters into something addressable, such as fields, tokens or a tree. A parser is only as good as its grammar, so input that does not match the expected shape needs handling.

### Partitioning · `Data Architecture`

Splitting a table into physical chunks by a key such as date or region, so a query that filters on that key reads one chunk instead of the whole table. Done well it is the single largest cost lever in a warehouse; done on a high-cardinality column it creates small files and hurts.

### pass · `Python`

A keyword that performs no operation, used where Python's syntax requires a statement or block but the code is not written yet. It lets a function or class be declared before it is implemented, since an empty block is a syntax error. A `pass` left in a live branch looks like success while returning `None`.

### Pearson's correlation coefficient · `Statistics`

A standardised measure of the strength and direction of the linear relationship between two continuous variables, ranging from `-1` to `+1`, with `0` meaning no linear association. In Python it is computed as `pearson_coef, p_value = stats.pearsonr(df['engine-size'], df['price'])` using `from scipy import stats`. The p-value says whether the association could be noise.

### Pie charts · `Visualization`

A pie chart is a circular statistical graphic divided into segments to illustrate numerical proportion, each wedge's angle encoding a share of the whole. It suits parts-of-a-whole with few categories, and overlapping text or crowded labels are the usual failure. Readable wedges often need a legend, a start angle, and percentages pushed outside with `pctdistance`.

### PII (personally identifiable information) · `Data Governance`

Any data that can identify a specific individual, directly through a name, address, email or government identifier, or indirectly by combination with other fields. Indirect identifiability is the trap: a postcode, birth date and gender can be enough to single a person out.

### Pinecone · `Generative AI`

A managed vector database service for storing and querying embeddings at scale, with low-latency approximate nearest-neighbour search and metadata filtering. It removes the operational work of running a vector index, which is what makes retrieval practical for small teams.

### Pipeline (scikit-learn) · `Machine Learning`

A `Pipeline` chains preprocessing and a final estimator into one object fitted and predicted as a unit, keeping transformations inside cross-validation rather than leaking across the data. Each step is a `(name, object)` tuple, so `Pipeline([('scale', StandardScaler()), ('polynomial', PolynomialFeatures(include_bias=False)), ('model', LinearRegression())])` scales, expands and fits in one call.

### Pivot table and heatmap · `Visualization`

A pivot table reshapes a grouped frame so one category labels the rows and another labels the columns, exposing an interaction rather than a single average. Build it with `df_gptest.groupby([...], as_index=False).mean()`, then `grouped_pivot.pivot(index='drive-wheels', columns='body-style')`, fill missing cells and render them with `ax.pcolor(grouped_pivot, cmap='RdBu')`. Because `pcolor` draws no axis labels, the tick labels must be set by hand.

### PixieDust · `Library`

An open-source library for interactive exploratory visualisation in Python and Jupyter notebooks, offering built-in chart types and data connectors behind a user interface. It is a library that behaves like an application, so charts are configured in the notebook rather than written as plotting code. Convenience comes at the cost of portability, since interactivity depends on the notebook front end.

### Platform as a Service (PaaS) · `Cloud`

A cloud service model providing a managed platform, including runtime, database and messaging services, on which a customer deploys code and data without managing servers. The provider owns the operating system, patching and scaling; the customer owns the application. It sits between infrastructure as a service and software as a service in retained control.

### Plotly · `Visualization`

An interactive, web-based charting library whose figures are serialised to JSON and rendered by the JavaScript Plotly library in a browser. Because the specification is data rather than an image, charts stay hoverable, zoomable and embeddable, and the same figure format is reachable from both Python and R. Portability depends on the runtime having the JavaScript layer available.

### Plotly Express · `Visualization`

A high-level plotting interface that builds a complete figure from one call, taking data and axis, colour and title arguments directly, as in `px.bar(x=grade_array, y=score_array, title='Pass Percentage of Classes')`. The lower-level `graph_objects` route creates an empty figure, adds traces and then a layout. Express trades fine-grained control for speed.

### PMML (Predictive Model Markup Language) · `Data Engineering`

An XML interchange format encoding predictive models, including inputs, transformations and parameters, so a model built in one tool can be scored by another. It separates model building from deployment, avoiding a re-implementation of the same logic. Only model types a tool supports can be exchanged, and some preprocessing must be restated in PMML.

### Polars · `Library`

A DataFrame library written in Rust with an Apache Arrow memory model, offering lazy evaluation, multi-threaded execution and a query optimiser. It is the performance-oriented alternative to pandas for data too large for comfortable single-threaded processing.

### Polynomial regression · `Machine Learning`

Regression fitting a polynomial of degree `n` rather than a straight line, adding curvature while remaining linear in its coefficients. With NumPy the two steps are visible: `f = np.polyfit(x, y, n)` estimates coefficients, `p = np.poly1d(f)` turns them into a callable model, and `Y_hat = p(x)` predicts. High degrees oscillate between the training points.

### PolynomialFeatures · `Machine Learning`

A scikit-learn transformer generating interaction and power terms from existing columns, so curvature and interactions can feed a linear model without being written by hand. `PolynomialFeatures(degree=2)` with `fit_transform(Z)` expands four predictors into fifteen columns, taking `(201, 4)` to `(201, 15)`. The column count grows combinatorially, so high degrees need regularisation.

### PostgreSQL · `Database`

A powerful open-source relational database management system emphasising extensibility and SQL compliance, with advanced features such as JSON support, full-text search and spatial data. It stores data in tables with schema enforced on write and supports transactions, indexes and joins. Extensions make the same engine host geospatial or document workloads, at some cost in portability.

### PRAGMA_TABLE_INFO() · `SQL`

A SQLite table-valued function that returns the schema of a named table as rows of column metadata. Querying `SELECT count(name) FROM PRAGMA_TABLE_INFO('CHICAGO_PUBLIC_SCHOOLS_DATA')` returned `[(78,)]`, and selecting `name`, `type` and `length(type)` lists each column. The declared type is what decides whether a later comparison is numeric or lexical, so a column declared `TEXT` will not compare as a number.

### Precision and recall · `Statistics`

Precision is `TP/(TP+FP)`, the share of predicted positives that are correct, and recall is `TP/(TP+FN)`, the share of true positives that were found. Both depend on the classification threshold, which is why they move together as it shifts. The harmonic summary is `F1 = 2PR/(P+R)`, useful when neither error type can be ignored.

### Predictive analytics · `Machine Learning`

The use of machine-learning techniques on historical data to predict future outcomes or events. Because the target lies in the future, evaluation must be out-of-sample and time-aware, and deployed models need monitoring for drift as the world moves away from the training period. A random split on temporal data overstates accuracy and is the standard mistake here.

### Predictive Modeling · `Machine Learning`

The building of models that predict future outcomes from historical data, as opposed to models that only describe or explain the past. It is the predictive half of an outcome pair. Its practical constraint is generalisation, so the quality of the estimate depends on how honestly the data was held out during development.

### Predictors · `Machine Learning`

The variables a model uses to predict an outcome, the same role called features, independent variables or regressors in other vocabularies. Knowing the synonym set matters when reading a data dictionary that uses a different word for the same column. Predictors are chosen for relevance to the target, and correlated ones make coefficients unstable.

### Prefect · `Data Engineering`

A Python-native workflow orchestrator in which ordinary functions become tasks and flows with retries, caching, scheduling and observability added by decorators. It is the low-ceremony alternative for teams that want orchestration without adopting a separate scheduling platform.

### Prescriptive Analysis · `Methodology`

The analytic approach that answers what should be done, rather than what happened or what will happen. Its techniques are optimisation models, simulation and decision analysis. It depends on the earlier stages, since prescribing an action requires a reliable prediction and a stated objective to optimise against.

### PRIMARY KEY · `SQL`

A constraint declaring one column, or a set of columns, whose values uniquely identify each row of a table, so a duplicate cannot exist. Declared as `PRIMARY KEY (ID)` alongside `ID int NOT NULL` in a table definition. It makes every row addressable, which `UPDATE ... WHERE`, joins and foreign keys depend on.

### Principal component analysis (PCA) · `Machine Learning`

A linear dimensionality reduction algorithm that simplifies data, reduces dimensionality and reduces noise while minimising information loss, projecting observations onto orthogonal directions of greatest variance. In a covariance matrix `[[3, 2], [2, 2]]` the diagonal entries are the variances of `X1` and `X2`, `3` and `2`, and the off-diagonal entry is their covariance, `2`. Input scaling changes the result.

### print() · `Python`

An output statement that prints the message or variable inside its parentheses to standard output. The signature is `print(*objects, sep=' ', end='\n')`, and each argument is converted with `str()` and written separated by `sep`. It is the fastest way to make a value visible and, alongside `type()`, to diagnose a wrong type; the returned value is always `None`.

### Prioritization · `Methodology`

Organising objectives by importance and impact, which is what turns a list of objectives into a feasible project. Scoping work this way is one reason business understanding avoids wasted time and resources. Without it, effort spreads across every stated objective and nothing is finished to a usable standard.

### Problem Solving · `Methodology`

The process of addressing challenges in order to achieve desired outcomes. It covers framing the problem, choosing an approach and closing the gap between the current and the intended state. A stated, measurable outcome is what makes the process finishable rather than open-ended.

### Project Jupyter · `Tool`

The open-source project behind notebook-style computing environments, supporting Julia, Python and R through Jupyter Notebook, JupyterLab and JupyterHub. Its documents combine live code, equations, visualisations and narrative text in one file. The kernel process is separate from the document, so notebooks can be run over remote or shared infrastructure.

### Prometheus · `Tool`

A freely available monitoring system that collects and stores metrics in real time from HTTP endpoints, exporters and agents. It adds visualisation, the PromQL query language and alerting over system and application health. It is pull-based by default, so targets must expose a scrape endpoint, and its local storage suits recent operational data rather than long-term archives.

### Prompt engineering · `Generative AI`

Designing the instructions, context and examples a model receives so that it reliably produces the wanted output. It is empirical work — specify the task, the format and the constraints, then test on representative cases — and it is the cheapest lever before fine-tuning.

### Prompt injection · `Generative AI`

An attack in which text the model treats as data contains instructions that hijack it, such as a retrieved document telling the model to ignore its rules and exfiltrate data. It is the defining security problem of grounded applications, and the defence is to separate instructions from data and to constrain what tools can do.

### Proprietary dataset · `Concept`

Data primarily owned and controlled by individuals or organisations, limited in distribution because it is sold under a licensing agreement. National-security, geological, geophysical and biological data are typical examples. The licence, not the format, is what restricts reuse, so availability, cost and permitted derivatives have to be checked before any analysis is published.

### Pseudonymisation · `Data Governance`

Replacing direct identifiers with a token or key so records can still be linked across tables, while keeping the mapping separate and protected. The data remains personal data under privacy law because re-identification is possible, but the risk of casual exposure drops sharply.

### Pull request · `Tool`

The way a developer requests that someone reviews and approves changes before they become final. It is a proposal to merge one branch into another, carrying the diff, discussion, reviews and status checks. Approval is a social gate rather than a technical one, so a passing test suite does not by itself authorise a merge.

### p-value · `Statistics`

The probability of observing a result at least as extreme as the one measured, assuming the null hypothesis is true. It is not the probability that the null is true, nor the size of the effect, and treating it as either is the most consequential misreading in applied statistics.

### Pyodide · `Library`

The Python runtime compiled to WebAssembly so that it executes inside a browser, shipped with a packaged scientific stack and a JavaScript interoperability layer. It is what makes a Python kernel possible in a browser tab with no server process. Package coverage is narrower than a full local installation, and memory and speed stay browser-bound.

### Pyolite · `Library`

The default kernel for JupyterLite, a Python kernel built on Pyodide, so a notebook running in a browser can `import pandas` exactly as any other kernel would. It supplies the execution layer while JupyterLite supplies the interface. Its packages arrive over the network on first use, and only the packages Pyodide ships are available.

### Python · `Language`

An open-source general-purpose programming language that has become the default for data science, used for databases, automation, web scraping, text and image processing, machine learning and analytics. Its data work comes from libraries grouped by purpose rather than from the core language. Readable syntax and that ecosystem explain the default, while interpreted execution makes heavy numeric loops slow unless vectorised.

### Python DB API (DB-API) · `Python`

A Python standard for accessing relational databases, which lets one program work with multiple kinds of relational database instead of a separate program per engine. The program is written against the standard, and the engine-specific part is the driver you import. Because the standard fixes only the interface, behaviour and error types still differ between drivers.

### PyTorch · `Library`

A Python deep-learning library covering regression and classification, built on dynamic computation graphs with automatic differentiation through autograd. Graphs are defined as the code runs, which makes debugging straightforward and suits research and custom architectures. It is a major source of pretrained models, and training speed depends on GPU availability.

---

## Q

*4 terms*

### Qlik · `Analytics & BI`

A BI platform whose associative engine keeps all relationships between fields in memory, so selecting a value highlights everything connected to it rather than filtering a pre-built query. That exploration model is its differentiator.

### Quantisation · `Machine Learning`

Reducing the numeric precision of a model's weights and activations — from 32-bit floats to 16, 8 or fewer bits — so it fits in less memory and runs faster, at some cost in accuracy. It is what makes large models servable on modest hardware, and the accuracy loss must be measured rather than assumed.

### Query plan · `SQL`

The tree of operations a database's optimiser chooses to satisfy a query — which table it scans first, which join algorithm it picks, and where it sorts or aggregates. It is what `EXPLAIN` prints, and reading it is the difference between guessing why a query is slow and knowing. The catch is that a plan is an estimate: it is built from statistics that can be stale, so the optimiser can choose badly for the data you actually have.

### Query string · `Web & APIs`

The part of a URL carrying data or parameters sent to a web server, typically in an HTTP GET request, so several values such as a name and an ID reach one endpoint. It begins with a `?`, followed by parameter and value pairs joined by `&`. Being visible in the URL, it is logged and cannot carry a secret.

---

## R

*37 terms*

### R · `Language`

A free-software statistical programming language used by statisticians, mathematicians and data miners for statistical software, graphing and data analysis. Adoption is heaviest in academia, healthcare and government, and it imports from flat files, databases, the web, SPSS and STATA. It is strongest where the workflow is statistical modelling and publication-quality graphics rather than production services.

### R² (coefficient of determination) · `Statistics`

A measure of how close the data lies to a fitted regression line, expressed as the percentage of variation in the response variable `y` explained by a linear model. Values run up to `1`, and a model with an R-squared close to `1` and a low MSE is generally a good fit. Low or negative values can indicate overfitting.

### Random forest · `Machine Learning`

An ensemble of decision trees, each trained on a bootstrap sample of the rows and a random subset of the features at every split, with their votes averaged or taken by majority. The randomness decorrelates the trees, which is what makes averaging reduce variance so effectively, and it is a strong default on tabular problems.

### Random number generation · `Statistics`

The provision of functions that produce random numbers and random data, used for simulations and statistical analysis. The modern interface is a generator object rather than a global seed: `rng = np.random.default_rng()`, then `samples = rng.normal(size=2500)`, giving an array of `shape=(2500,)`. Generators are reproducible only when seeded deliberately, so an unseeded simulation cannot be rerun exactly.

### Randomisation · `Statistics`

Assigning units to conditions by chance so that measured and unmeasured differences are balanced across groups on average. It is the one mechanism that licenses a causal claim from a comparison, and its failure — assignment by convenience or by user choice — is what turns an experiment back into an observational study.

### range() · `Python`

A function generating a sequence of numbers for iterating in a loop, written `range(start, stop, step)` and producing numbers from `start` up to but excluding `stop`. It supplies a counter without a `while` loop and without a manual increment, which is where off-by-one errors come from. The object computes values lazily.

### Rapid Elasticity · `Cloud`

The ability to scale cloud resources up or down quickly in line with demand, releasing capacity when it is no longer needed. Resources follow the workload rather than being provisioned for the peak in advance. Elasticity depends on automation and on the workload being able to start and stop cleanly, so stateful services scale less freely than stateless ones.

### read_csv() and read_excel() · `Library`

The two entry points that turn a file into a DataFrame, called as `df = pandas.read_csv(csv_path)` and `df = pandas.read_excel(xlsx_path)`. They are the single line that makes a dataset analysable. Path handling, delimiters, quoting and encoding bite first on CSV, while Excel needs an extra engine such as `xlrd` or `openpyxl` installed.

### Reading a file · `Python`

Reading offers one method per granularity: `read()` returns the whole remaining contents as one string, `readline()` one line at a time, and `readlines()` a list of lines, while iterating the file object also yields lines. The choice decides whether you hold one giant string, a stream of lines or a list. Reads consume the file position.

### Real-time inference · `MLOps`

Scoring a single request as it arrives, usually over HTTP and with a latency budget in milliseconds. It requires the model in memory, the features available at request time, and an answer to what happens when the scoring service is unavailable.

### Receiver Operating Characteristic (ROC) · `Statistics`

A statistical curve, originally developed for military radar, used to assess binary classification models; the name preserves its origin, in which the receiver is the radar receiver. It plots true-positive rate against false-positive rate as the decision threshold varies. Because it ignores class balance, it can flatter a model on imbalanced data.

### Red Hat OpenShift · `Cloud Platform`

A container application framework based on Kubernetes, adding automation, scalability and security for creating, deploying and managing containerised applications and microservices. It packages the cluster, the build pipeline and the operational controls into one platform. The convenience of the platform also means its abstractions and costs shape what a team can change.

### Redeployment · `Machine Learning`

Implementing a refined model together with intervention actions after incorporating feedback and improvements. It is where the cyclicity of a data science methodology becomes observable, since the loop returns to earlier steps instead of finishing once. It is also the point at which ethical considerations about the deployed intervention get named rather than assumed.

### Reduce Process · `Data Engineering`

The second step in MapReduce, in which the results of the map phase are aggregated per key to produce the final output, written `reduce(k2, list(v2)) -> list(k3, v3)`. Grouping by key is what makes the aggregate local and parallelisable. All values for a key must reach the same reducer, so a skewed key can dominate the runtime.

### Reductions with axis · `Python`

Reductions along a chosen axis, where `x.max(axis=1)` on a two-dimensional array returns `array([4, 8, 13])`, the maximum within each row. `axis=0` collapses rows to give one value per column, `axis=1` collapses columns to give one value per row, and the result drops a dimension. The wrong axis silently yields the transpose.

### Regression · `Machine Learning`

Supervised learning that predicts numerical values, that is a continuous output rather than a class label. It is evaluated with MAE, RMSE and R-squared on held-out data, and diagnosed through residuals rather than by the fit alone. A good fit metric can still hide structure in the errors, so residual plots belong in the workflow.

### Regularisation · `Machine Learning`

A penalty on a model's coefficients that trades training fit for stability on new data; ridge shrinks them toward zero and Lasso can drive some exactly to zero, making it a variable selector. On synthetic points from `y = 4 + 3x` with 5 outliers between `+50` and `+100`, ridge performed similarly while Lasso outperformed both.

### Reinforcement learning · `Machine Learning`

Learning conceptually similar to human learning processes, as in a mouse in a maze, a walking robot, chess or go, where an agent acts in an environment and learns a policy maximising cumulative reward. Feedback arrives as rewards rather than labelled examples, so the agent must explore. Reward is delayed and must be designed.

### Relational Database Management System (RDBMS) · `Database`

A database management system that stores data in relations, that is tables, and manages it with SQL. It enforces schema on write and provides ACID transactions, indexes and joins, with MySQL and PostgreSQL as open-source exemplars. The schema and constraints are what make queries predictable; the same structure is what makes evolving the model costly once data is loaded.

### Relational model · `Database`

The data model that stores data in tables and is the most used data model, allowing for data independence. Data independence means how the data is physically stored can change without changing the queries written against it. It is the model queried by nearly all analytics SQL, and its tabular shape is why joins and keys carry so much weight.

### Relative Misclassification Cost · `Statistics`

A parameter in model building used to tune the trade-off between true-positive and false-positive rates. It converts a statistical curve into a business decision by stating how much worse one kind of error is than the other. Its value is a judgement about consequences, not a property of the data.

### Repository · `Tool`

The project folder set up for version control, holding a `.git` object store plus a working tree, so code and its change history travel together and collaboration becomes possible. The same structure hosted elsewhere is a GitHub repository. Committing records snapshots locally, so nothing is shared until it is pushed.

### Reproducibility · `MLOps`

The ability to obtain the same result again from the same inputs: the same code version, data version, environment, random seeds and configuration. It is the property that makes a result auditable and a bug fixable, and it fails quietly when any of those is unrecorded.

### Request body · `Web & APIs`

The part of an HTTP request carrying data to a server, used by a POST request where a GET puts its data in the URL. That is the difference between a request that can be bookmarked and one that cannot, and in `requests` the `data=` argument rather than `params=`. It can carry sensitive payloads.

### requests (the library) · `Library`

A Python library that allows you to send HTTP/1.1 requests easily, with a small function surface for verbs, parameters and response handling. It is the modern counterpart to the older `urllib`, which also works with URLs and makes HTTP requests, including fetching web content and handling cookies. It retrieves a response but does not parse or render it.

### Residual analysis · `Statistics`

The inspection of differences between predicted and actual values, because aggregate statistics alone do not say where a model did well or poorly. A residual histogram here was normally distributed, with mean error `-$1,250` and standard deviation `$50,583`, while a sorted scatter showed average error against median house price rising from negative to positive. The two readings differ.

### Resource Pooling · `Cloud`

The sharing and dynamic assignment of computing resources among multiple consumers, which promotes economies of scale and cost efficiency. Capacity is drawn from a common pool instead of being dedicated per tenant. Sharing also means noisy neighbours and variable performance, which is why isolation and quotas matter.

### Responsible AI · `Data Governance`

The practice of building and deploying AI systems with explicit attention to fairness, transparency, accountability, safety and privacy. Concretely it means documented intended use, measured bias across groups, explainable decisions and a named owner for harm.

### Responsible web scraping · `Web & APIs`

The practice of scraping within the terms a website sets, respecting its rules and the expectations of the people whose data is collected. This is the normative constraint on any crawler: what the tooling makes technically possible is not automatically permitted. Practically it means checking terms of service and `robots.txt`, limiting request rates and identifying the client.

### REST API · `Web & APIs`

An API communicating over the internet in the Representational State Transfer style, where resources are addressed by URL, manipulated with standard HTTP verbs and stateless between requests. It comes with rules for communication, for the request and for the response. Statelessness lets requests be retried and scaled independently, and is why each request carries its own credentials.

### Retrieval-augmented generation (RAG) · `Generative AI`

A pattern that retrieves relevant passages from a knowledge base and puts them into the prompt so the model answers from supplied evidence instead of from memory. It reduces hallucination and makes citations possible, and its quality is bounded by retrieval — if the right passage is not retrieved, no prompt can recover it.

### return and implicit None · `Python`

A `return` statement exits a function immediately with the given value, while a function with no return statement returns `None` by default, and a bare `return` also returns `None`. This explains outputs such as `print(fib(0))` printing `None`, and mutation-only methods whose apparent result is `None`. Assigning such a call and using it later is how the mistake surfaces.

### Reverse ETL · `Data Architecture`

Pushing modelled data from the warehouse back out into operational tools — CRM, support desk, ad platform — so that a computed segment or score is acted on where work happens. It closes the loop that usually ends at a dashboard.

### Ridge regression · `Machine Learning`

A linear model with an L2 penalty on the coefficient sizes, which reduces variance at the cost of some bias. In scikit-learn it is fitted with `from sklearn.linear_model import Ridge`, then `RidgeModel = Ridge(alpha=1)`, `RidgeModel.fit(x_train_pr, y_train)` and `yhat = RidgeModel.predict(x_test_pr)`. The `alpha` value controls how strong the penalty is, and features need scaling for the penalty to treat them comparably.

### RLHF · `Generative AI`

Reinforcement learning from human feedback: humans rank model outputs, a reward model is trained on those preferences, and the language model is optimised against it. It is the technique that made assistants helpful and polite, and it also imports the preferences of whoever supplied the labels.

### Role-based access control (RBAC) · `Data Governance`

Granting permissions to roles rather than individuals, so access follows a person's function and is revoked by changing their role assignment. It is auditable and scalable, and its recurring failure is role sprawl, where everyone accumulates the access of every job they have held.

### RStudio · `R`

The integrated development environment for writing and running R code, arranged in panes for the Code Editor, the Console, Workspace History, and Files, Plots, Packages and Help. It gives interactive execution alongside object inspection, which is how most R analysis is done. The environment is separate from the language, so scripts stay portable while project settings do not.

---

## S

*91 terms*

### Sample size · `Statistics`

The number of observations needed to detect an effect of a stated size with a chosen power and significance level, computed before the study rather than after it. Deciding it afterwards turns an experiment into a search for a favourable stopping point.

### Sampling bias · `Statistics`

A distortion created when the sample is collected in a way that systematically favours some parts of the population over others. No amount of analysis repairs it, because the missing observations are missing by construction — which is why how the data was gathered matters more than how large it is.

### Scala · `Language`

A general-purpose language with functional programming and a strong static type system, built to address Java's shortcomings and interoperable with it through the JVM. It is the language Apache Spark is written in, so much of Spark's API is legible as Scala. Type safety and JVM interoperability are the strengths; compile times and a steeper curve are the costs.

### Scatter plots · `Visualization`

A scatter plot in two dimensions compares variables by plotting one value against another. It resembles a line plot in mapping independent and dependent variables, but the points are not connected by a line, so the data expresses a trend rather than a sequence. A fitted curve over the points summarises them and is not a forecast.

### Schema registry · `Data Engineering`

A central service that stores the versions of the schemas flowing through a streaming platform and enforces compatibility rules between them. It turns a producer's accidental breaking change into a rejected publish rather than an outage in every consumer.

### Schema-on-read · `Data Architecture`

Interpreting the structure of data only when it is queried, so raw files can be stored as they arrive and the schema is applied by the reader. It is flexible and defers commitment, at the cost of discovering data defects at query time rather than at load time.

### Scikit-learn · `Library`

The Python machine-learning library for regression, classification and clustering, exposing a uniform estimator interface of `fit`, `predict` and `transform` across models. Pipelines, train-test splitting and cross-validation come from the same package. The uniform interface makes algorithms interchangeable, at the cost of hiding algorithm-specific options and offering no native support for very large or streaming data.

### SciPy · `Library`

One of Python's scientific-computing libraries, grouped with Pandas, NumPy and Matplotlib. It provides algorithms built on NumPy arrays for optimisation, integration, interpolation, linear algebra, signal and image processing, and statistics. It fills the gaps the array library leaves, so it is imported for the specific submodule needed rather than as a whole.

### Scope (local and global variables) · `Python`

The scope of a variable determines where you can access or modify that variable. A name bound inside a function is local to it, while a name bound at module level is global and readable from inside functions. Assignment inside a function creates a new local name unless declared `global`, so a variable can appear modified yet stay unchanged.

### Scrapy · `Library`

An open-source and collaborative web crawling framework for Python, used to extract data from websites. It is a framework rather than a library: spiders and item pipelines are declared and it runs the queue, concurrency and throttling, which suits crawling many pages while following links. Retrieval still returns only what the server sends.

### Seaborn · `Visualization`

A Python visualisation library specialised in heat maps, time series and violin plots, built on Matplotlib with a DataFrame-first API and statistical aggregation. Passing a frame and column names is enough to draw a distribution or a regression with a confidence band. It complements rather than replaces Matplotlib, since final layout tweaks usually fall back to the underlying library.

### Segmentation · `Analytics & BI`

Dividing a population into groups with meaningfully different behaviour or needs, using business rules or clustering, so that analysis and action can be targeted. A segment is useful only if it is stable, actionable and distinguishable.

### SELECT · `SQL`

The SQL statement that projects columns from a table, as in `SELECT * FROM FilmLocations;`, where `*` means every column in table order. Naming columns explicitly is what makes a query stable and gives the result a defined shape. The wildcard is convenient for inspection, but it breaks or silently changes when a table's columns change.

### select_dtypes() · `Library`

A DataFrame method returning only the columns matching a type-based criterion, for example `df.select_dtypes(include=[np.number])` for numeric columns. It guards computations needing one dtype, such as `df.corr()`, which raises or silently drops columns on mixed-dtype frames where a date stored as `str` is a common culprit. It is the type-based counterpart to `df.drop(columns=...)`.

### Selection bias · `Statistics`

A distortion introduced by how units enter the analysis — who volunteers, who survives a filter, who answers the survey. It shifts the distribution of the sample away from the population the conclusion is supposed to describe.

### Selenium · `Library`

A tool used for controlling web browsers through programs and automating browser tasks. It covers the case other scrapers cannot, a page whose table is rendered by JavaScript and never appears in the retrieved markup: a real browser is driven, elements are waited for, and their contents read. It needs a browser binary plus a driver.

### self parameter · `Python`

The first parameter of a constructor, referring to the instance being created, and required in instance methods. It is the explicit receiver that other languages hide, since without it a method would have no way to know which instance's attributes it is reading. Writing an instance method without it raises a type error at call time rather than at definition.

### Self-service analytics · `Analytics & BI`

Giving business users the governed ability to answer their own questions without a data team in the loop. It scales analysis across an organisation and only works when the underlying models and metric definitions are trustworthy, otherwise it scales disagreement instead.

### Semantic layer · `Data Architecture`

A governed definition layer that sits between the warehouse tables and the BI tools, where metrics such as revenue or active user are defined once in code and reused everywhere. It removes the situation in which three dashboards report three different numbers for one word.

### Semantic search · `Generative AI`

Retrieval ranked by meaning rather than by exact term matching, implemented by embedding the query and the documents into one vector space. It handles paraphrase and synonymy that keyword search misses, and it loses the precision of an exact match unless the two are combined.

### Semi-supervised learning · `Machine Learning`

Training with a small labelled set and a large unlabelled one, using the unlabelled data to shape the decision boundary through pseudo-labelling, self-training or consistency regularisation. It is worth the complexity when labelling is expensive and raw data is abundant.

### Sequence · `Python`

In its mathematical sense, a sequence is formally defined as a function whose domain is an interval of integers, an ordered mapping from positions to values. In Python usage the word names any ordered collection supporting indexing and length, such as a list, a string or a tuple. Both senses share order and position.

### Serialisation · `Data Engineering`

Converting an in-memory object into a byte stream for storage or transport, and back again, using a format such as JSON, Avro, Parquet or Protocol Buffers. The choice decides file size, read speed, schema evolution and whether the data is human-readable.

### Series · `Library`

A one-dimensional labelled array of values, the column-like structure of Pandas. It carries attributes and methods including `values`, which returns a NumPy array, `index` for labels, `shape`, `size`, aggregations such as `mean()` and `max()`, `unique()` and `nunique()`, `sort_values()`, `isnull()` and `apply()`. Operations align on the index rather than position, so mismatched labels give unexpected results.

### Serverless computing · `Data Engineering`

Running code on demand where the provider allocates and bills the underlying capacity per invocation or per second, with none visible to the developer. It removes cluster management and suits bursty, event-driven work, at the cost of cold starts, execution time limits and less control over the runtime.

### Set operations · `Statistics`

Set operations in Python refer to mathematical operations performed on sets, unordered collections of unique elements. Membership work covers adding, removing and verifying elements, alongside union and intersection. They answer cleaning questions directly, such as which customers appear in both lists or only in one, without loops; because sets are unordered, output loses any original order.

### Sets in Python · `Python`

A set is an unordered collection of unique elements, useful for tasks such as removing duplicates and performing set operations like union and intersection. Its constructor is itself the deduplication operation, which makes it the fastest way to reduce a list to distinct values. Elements must be hashable, and iteration order is not guaranteed.

### Shadow deployment · `MLOps`

Sending live traffic to a new model in parallel with the incumbent without acting on its output, then comparing predictions and latency offline. It exposes failure modes with no user-visible risk, which is why it is the safest first step for a risky model.

### Sharding · `Data Architecture`

Horizontally splitting a dataset across independent machines by a shard key, so each node holds and serves a subset. It is how write-heavy systems scale beyond one server, and the choice of key decides whether the load is even or one shard becomes a hotspot.

### Shapley values · `Machine Learning`

A way to attribute one prediction among a model's input features, borrowed from cooperative game theory: a feature's contribution is its average marginal effect over every possible ordering of the other features. It is the attribution method that satisfies the fairness properties people usually want — efficiency, symmetry, dummy and additivity — which is why it underpins SHAP. Exact values cost exponential time, so implementations approximate, and correlated features split credit in ways that are easy to misread.

### Shark · `Library`

A query engine included in the Spark stack as its historical SQL-on-Spark layer, letting SQL run over Spark data. It was discontinued in favour of Spark SQL, which is the engine to use for that job now. The reason to know it is recognition, since older documentation and job descriptions still name it.

### SimpleImputer · `Machine Learning`

The scikit-learn transformer that fills missing values, the library equivalent of `fillna`, called as `SimpleImputer(strategy='median')` and fitted inside a pipeline. Being inside the pipeline makes imputation leakage-free, since the median is learned from the training fold and applied to the validation fold rather than computed over the whole frame. `median` suits a skewed column and `most_frequent` a categorical one.

### Simpson's paradox · `Statistics`

The situation in which a trend visible in every subgroup reverses when the subgroups are combined, because the groups differ in size and in baseline rate. It is the standard demonstration that an aggregate statistic can point the opposite way from the data it summarises.

### Skewness · `Statistics`

The asymmetry of a distribution: positive skew has a long right tail, negative skew a long left tail. It tells you that the mean sits away from the bulk of the data and that the median is the more representative summary.

### Skills Network Labs (SN Labs) · `Tool`

An IBM-hosted cloud workspace that provides ready-to-run Jupyter notebooks and Spark clusters, so analysis can be done from a browser without installing a local environment. Convenience is the point; the environment is disposable and not a substitute for a reproducible local setup.

### Slicing in Python · `Python`

Slicing returns a portion from a defined list, or extracts a portion of a string, written `substring = string_name[start:end]`. The start is inclusive and the end exclusive, and omitting either extends to the boundary of the sequence. It is how fixed-width fields, dates and IDs are pulled apart from text, and unlike indexing it does not raise.

### Slowly changing dimension (SCD) · `Data Architecture`

The design question of what to do when a dimension attribute changes — a customer moves city. Type 1 overwrites the old value, type 2 adds a new row with validity dates so history is preserved, and type 3 keeps a previous-value column; only type 2 makes past reports reproducible.

### Snowflake · `Cloud Platform`

A cloud data warehouse whose defining architecture separates storage, compute and cloud services, so several virtual warehouses query the same data at once without contending for resources. It is fully managed and multi-cluster, and it handles semi-structured JSON natively alongside relational tables.

### Snowflake schema · `Data Architecture`

A dimensional model in which dimension tables are normalised into further tables, so a product dimension points at separate category and supplier tables. It saves storage and removes redundancy, but each extra join costs query time and comprehension.

### Snowpark · `Cloud Platform`

Snowflake's developer framework that runs Python, Java or Scala code inside the warehouse, so DataFrame transformations execute next to the data instead of extracting it to a separate cluster. It removes the copy-out step that a separate Spark cluster would require.

### sns.regplot() · `Library`

A Seaborn function drawing a scatter plot with a fitted regression line and a confidence band, taking a continuous predictor against the target. The recipe is `plt.figure(figsize=(15, 10))` with `sns.set(font_scale=1.5)` and `sns.set_style('whitegrid')`, then `ax = sns.regplot(x='year', y='total', data=df_tot, color='green', marker='+', scatter_kws={'s': 200})`. It shows association rather than causation.

### Software as a Service (SaaS) · `Cloud`

A cloud service model delivering a complete, provider-managed application consumed over the network, so users reach it through a browser rather than installing it. The customer owns only its data, configuration and users. Control is correspondingly limited, and integration, export and data residency depend on what the provider exposes.

### Solution Deployment · `Methodology`

Implementing and integrating the data science model into the business or organisational workflow, the stage where the model is put to the ultimate test. Release typically begins with a limited group of users or in a test environment before wider rollout. Deployment decisions about monitoring, rollback and ownership are what decide whether the model keeps working once it is live.

### Solution Owner · `Role`

The individual or team responsible for overseeing the deployment and management of a data science solution. It is a stakeholder role defined by accountability rather than by a specific function, so it answers for the solution's continued operation and outcomes. Where no one holds that accountability, models persist unmonitored after the project ends.

### Sorting · `Python`

Sorting arranges values into order, and the two Python forms differ: `sorted(Ratings)` returns a new list, while a list's own `sort()` method reorders in place and returns `None`. Applied to `(0, 9, 6, 5, 10, 8, 9, 6, 2)`, `sorted` gives `[0, 2, 5, 6, 6, 8, 9, 9, 10]`, so the input type need not match the output type.

### Spark Streaming · `Data Engineering`

Spark's stream-processing component, which processes data as discretised streams or micro-batches rather than handling each event individually. It was superseded by Structured Streaming, which keeps the same micro-batch model behind a declarative API. Micro-batching gives throughput and fault tolerance at the cost of per-event latency.

### Spilling to Disk · `Data Engineering`

Writing data temporarily to disk when memory is exhausted, so that processing continues instead of failing. It is a symptom rather than a goal: chronic spilling usually indicates wrong partitioning or key skew rather than insufficient RAM, so adding memory treats the effect while leaving the cause. The immediate cost is slower execution as data moves across the memory boundary.

### SPSS Modeler · `Tool`

A commercial visual tool for building predictive models by wiring nodes together on a canvas rather than writing code. It is available inside Watson Studio Desktop and exports finished models as `PMML`, so another platform can score with them. Choose it when analysts rather than programmers own the model.

### Spyder · `Tool`

An integrated development environment for Python that combines code, documentation and visualizations on one canvas, with a Variable Explorer, an IPython console and a debugger. The neighbouring tools are easily confused: Jupyter is a notebook interface, RStudio is the R IDE, and Anaconda Navigator only launches environments. Reach for it when you want an object inspector beside your script.

### SQL magic · `SQL`

Magic commands are special commands in IPython: line magics carry a single `%` and act on one line, while cell magics carry `%%` and act on a whole cell. The `ipython-sql` extension, loaded with `%load_ext sql`, supplies `%sql` and `%%sql`, so SQL goes in the cell and a result set comes out. That makes an interactive document a database client.

### SQLAlchemy · `Library`

A Python SQL toolkit and object-relational mapper that lets one API reach many database engines, and the library `ipython-sql` uses to talk to databases. Every SQL magic connection string is therefore a SQLAlchemy URL of the form `dialect://user:pass@host/database`, which explains why `%sql sqlite:///file.db` has three slashes: the empty host still claims its separator.

### SQLite 3 · `Database`

An in-process Python library implementing a self-contained, serverless, zero-configuration transactional SQL database engine. In-process means there is nothing to start, serverless means no host, port, user or grant, and zero-configuration means a file path becomes a database, yet it remains transactional so `commit()` and `rollback()` exist.

### sqlite3.connect() · `Library`

Opens a connection to a SQLite database and implicitly creates the database file if it does not yet exist, which is the fact that makes SQLite convenient for teaching and prototyping. The argument is a path or the literal `':memory:'`; a relative path resolves against the process working directory, and the tilde shortcut is not expanded.

### sqlite_master · `SQL`

The system table in which SQLite records its own schema: every table, index, view and trigger appears there as a row. Running `cursor.execute("SELECT name FROM sqlite_master WHERE type='table';")` lists the tables available in any database file, which is the portable first query to issue against a database you did not create.

### SSH protocol · `Web & APIs`

A method for secure remote login from one computer to another, built on public-key cryptography so a private key proves identity without sending a password. It is how a developer authenticates to a Git host and how automated jobs push commits without entering a credential per operation. Key-based access also means the private key file becomes the secret to protect.

### Staging area (index) · `Tool`

The intermediate area in Git that holds the changes selected for the next commit: `git add` moves changes from the working directory into the index, and `git commit` turns the index into history. Because staging is explicit, a commit can contain a deliberate subset of your edits rather than everything you happened to save.

### Stakeholders · `Methodology`

The individuals or groups with a vested interest in a data science model's outcome and its practical application, such as solution owners, marketing, application developers and IT administration. They are engaged because diverse specialties ensure the model's applicability, and because they evaluate the result and feed findings back. Skipping them is how technically sound models go unused.

### Standard Deviation · `Statistics`

A measure of variability or dispersion in a dataset, computed as `σ = √(Σ(xᵢ − x̄)² / n)` for a population, with `n − 1` for the sample estimate. It is the pair to the mean, since a difference between averages cannot be judged meaningful without knowing how spread out each group is. It shares the units of the data.

### Standardisation (feature scaling) · `Machine Learning`

Rescaling every input feature to a common scale so that the model does not inadvertently favour any feature because of its magnitude. It matters most for methods that measure distance or penalise coefficients, where a feature recorded in large units dominates one recorded in small units purely by arithmetic.

### Star schema · `Data Architecture`

A dimensional model with one central fact table surrounded by denormalised dimension tables that it references by key. The shape makes joins simple and predictable, which is why it remains the standard model for BI and columnar warehouses.

### Stata · `Tool`

A commercial software package used for statistical analysis, driven by scripts called `.do` files. It is strongest in econometrics and in panel and survey data, where its built-in commands for those designs save considerable work. It is proprietary and licence-bound, which is why open alternatives are often preferred for sharing.

### State and behaviour · `Python`

The two characteristics every object has: state is the attributes or data that describe the object, and behaviour is the actions or methods the object can perform. The pair is the cleanest test for whether something should be a class at all, since an object with no state is better expressed as a plain function.

### Statistical Analysis · `Statistics`

The application of statistical methods to analyze data and solve problems, forming the method family behind the diagnostic approach that asks why something happened. Its emphasis is explanation rather than prediction, so it delivers estimates, tests and their uncertainty rather than scores. It underlies every later claim of cause.

### Statistical distributions · `Statistics`

A way of describing the likelihood of different outcomes based on a dataset, either discrete, as in the Bernoulli, binomial and Poisson distributions, or continuous, as in the normal, t, chi-square, exponential and log-normal. They form the assumption layer beneath statistical tests and confidence intervals, so choosing a distribution the data does not follow quietly invalidates the conclusion.

### Statistical power · `Statistics`

The probability that a test detects an effect of a given size when that effect truly exists, conventionally targeted at 80 %. It rises with sample size and effect size and falls with noise, and an underpowered study wastes its data by returning inconclusive results.

### Statistical Significance Testing · `Statistics`

The procedure of asking whether an observed difference or relationship is distinguishable from chance: state a null hypothesis of no effect, compute a test statistic from the data, and read a p-value as the probability of a result at least this extreme if the null were true. It controls a long-run error rate rather than proving anything, and significance is not importance — a trivial effect becomes significant once the sample is large enough.

### Statistics · `Statistics`

The study of data collection, analysis, interpretation and presentation. It supplies the vocabulary that every analytic approach borrows, from summary measures to tests and intervals, and it insists that a number be reported with its uncertainty. Descriptive work compresses what was observed, while inferential work reasons beyond the observed sample.

### statsmodels · `Library`

The Python statistics library, contrasted with scikit-learn by purpose: scikit-learn is used to make predictions, while statsmodels is used to understand relationships and statistics. It reports coefficients, standard errors, p-values and diagnostics alongside the fitted model, which makes a result defensible when the question is why rather than what. Its formula interface accepts an R-style `y ~ x` specification.

### Stored procedures · `SQL`

A set of SQL statements stored and executed on the database server, so callers invoke one name instead of shipping a statement each time. That centralises logic and reduces round trips, and can restrict what a caller may do. The logic is engine-specific, harder to version control, and can hide behaviour from whoever reads the application code.

### Storytelling · `Analytics & BI`

The art of conveying your message or ideas through a narrative structure that engages, entertains and resonates with the audience. Its built-in tension is balancing a clear, coherent, simple story against conveying all the complexities you might find within the data. The usual resolution is a headline conclusion supported by detail available on request.

### Stratified sampling · `Statistics`

Dividing the population into strata that differ in an important way and sampling within each, so the sample reproduces the population's composition. It reduces variance relative to simple random sampling and guarantees that small but important groups appear at all.

### Stream processing · `Data Architecture`

Processing records continuously as they arrive, with latency measured in milliseconds to seconds. It answers questions that cannot wait for the next batch, and it costs complexity: ordering, windowing, late data and exactly-once semantics all have to be handled.

### Stride value · `Python`

In Python the stride of a slice is its third argument, the step in `s[start:end:step]`, so `s[::2]` takes every second element and a negative step walks backwards. The term also describes the number of bytes from one row of pixels in memory to the next in image processing. The surrounding context decides which sense is meant.

### String methods · `Python`

The core method calls on a Python string: `len()` returns the length, `lower()` and `upper()` change case, `replace()` swaps substrings, `split()` breaks the string into a list on a delimiter, and `strip()` removes leading and trailing whitespace. All of them return a new string rather than altering the original; note that `split()` with no argument splits on runs of whitespace.

### String patterns · `SQL`

Pattern matching in SQL uses `LIKE` with wildcards, where `%` matches any sequence of characters including none and `_` matches exactly one character, so `WHERE firstName LIKE 'R%'` finds every name beginning with R. Everything outside the wildcards is literal. A leading wildcard prevents index use, so such filters are slow on large tables.

### stringr · `R`

The R library for manipulating strings, offering a consistent `str_*` API built on regular expressions for detecting, replacing, extracting, splitting and trimming text. Consistency is the point: one argument order and one set of conventions across the whole family, instead of the mixed base-R alternatives. It pairs naturally with the tidyverse's data-frame and pipe idioms.

### Strings · `Python`

In Python, strings are arrays of bytes representing Unicode characters, so text is an ordered and immutable sequence. They are the default shape of most received data, whether CSV fields, JSON values or API responses, and their operations reappear at scale later. Immutability means every method returns a new string, and indexing or slicing yields substrings rather than views.

### Structured data · `Data Engineering`

Data organized according to a predefined schema and typically stored in a database, so each record carries the same named fields in the same types. The schema is what makes querying, joining and validating possible, and it is the counterpart of unstructured data such as free text, images and audio. The two shapes need different preparation toolkits.

### Structured Query Language (SQL) · `Language`

A declarative language for managing data in a relational database: you state the result you want rather than the steps to compute it. Its surface covers projection and filtering, joins, aggregation, common table expressions, window functions, data definition and transactions. Portability across engines is partial, since types, functions and catalogue names differ.

### Subplots · `Visualization`

A layout that places several charts in one figure by creating a grid and drawing on each cell. Typical usage is `fig, axes = plt.subplots(2, 1, figsize=..., sharex=True)` followed by `axes[i].plot(...)`, where `sharex=True` ties the horizontal axes together. When more than one row or column is requested, `axes` is an array that must be indexed.

### Subqueries · `SQL`

Subqueries, or subselects, are regular queries placed within parentheses and nested inside another query, appearing in the `WHERE` clause or the `FROM` clause. They turn one query's answer into another query's input, which is how rows get compared against an aggregate such as an average. A scalar subquery supplies one value for `=`; a row-returning one feeds `IN`.

### Subset and superset · `Statistics`

The subset method determines whether two or more sets stand in a containment relation: `issubset()` answers whether all of mine are in yours, and `issuperset()` the reverse, both returning `True` or `False`. Containment is the cheapest validation available, since checking that a set of required columns is contained in a dataset's columns costs one call.

### Substring · `Programming`

A substring is a sequence of characters that are part of an original string, obtained by slicing or by extraction methods such as `split()` and `replace()`. Containment, prefix and suffix tests and replacements all operate on substrings and none of them mutates the original: `"ell" in "Hello"` returns `True`, while `str.startswith()` and `str.endswith()` answer the boundary questions.

### Supervised learning · `Machine Learning`

Learning from labelled examples, using regression when the target is a numerical value and classification when it is a category, with the labels supplying the error signal the model is measured against. Its ceiling is set by the labels it was given, so a model can only learn distinctions the training data annotates. Labelling effort is usually the binding constraint.

### Support vector machine (SVM) · `Machine Learning`

A supervised learning technique for classification and regression that divides data into two classes by finding a decision boundary, a hyperplane that maximizes the margin between them. Scikit-learn provides kernel functions such as linear, polynomial, RBF and sigmoid, and the method is effective in high-dimensional spaces and robust to overfitting. The RBF kernel needs `C` and `gamma` tuned.

### Surrogate key · `Data Architecture`

A system-generated integer that identifies a row in a dimension or fact table, independent of any business key. It decouples the warehouse from changes in source identifiers and makes type 2 history possible, since one business key can own several surrogate keys.

### Survivorship bias · `Statistics`

Drawing conclusions from the cases that survived a selection process while the failures are invisible — funds still trading, companies still listed, students who graduated. It systematically overstates success, and the fix is to find and include the cases that dropped out.

### Synthetic control · `Statistics`

A causal method for the case where a single unit was treated — one city, one country, one company — and no individual control is comparable. A weighted combination of untreated units is built to track the treated unit's pre-treatment history, and that synthetic counterfactual is projected forward to estimate the effect. Its credibility rests entirely on the pre-period fit: if the synthetic unit cannot follow the real one before the intervention, the gap afterwards means nothing.

### Synthetic Data · `Machine Learning`

Artificially generated records that reproduce the statistical properties of real data, used to augment a scarce or imbalanced training set, to protect privacy, or to test a pipeline where real data is unavailable or sensitive. Its value depends entirely on how faithfully it reflects the real distribution.

### System catalogue · `SQL`

The metadata tables each relational engine keeps to describe its own objects. Names are product-specific: in DB2 the catalogue is `SYSCAT.TABLES`, in SQL Server it is `information_schema.tables`, in SQLite it is `sqlite_master`, and in MySQL it is `SHOW TABLES`. Querying it is the fastest way to learn what is inside a database you did not create.

### System prompt · `Generative AI`

The instruction that sets a model's role, constraints and output format before any user turn, and that the application rather than the user controls. It is where tone, refusal behaviour and formatting rules are fixed.

---

## T

*29 terms*

### Tableau · `Analytics & BI`

A visual analytics platform in which analysis is built by dragging fields onto shelves, with extracts for performance and a calculation language for derived measures. Its strength is exploratory speed for an analyst; its cost is licence and the tendency to duplicate metric logic outside the warehouse.

### TCP/IP network · `Web & APIs`

A network in which connected devices communicate through the TCP/IP protocol suite, the stack the Internet uses. IP handles best-effort addressing and routing of packets, while TCP adds reliable, ordered delivery on top of it, so a lost packet is retransmitted rather than silently dropped. Application protocols such as HTTP are layered above them.

### Temperature · `Generative AI`

A sampling parameter that scales the randomness of token selection: near zero makes the model nearly deterministic and repeatable, while higher values increase diversity at the cost of coherence. It is the first knob to set for a task that needs consistency rather than creativity.

### TensorFlow · `Library`

A deep-learning framework with a Python interface and a core written in C++, aimed at production and deployment rather than only experimentation. It operates at a lower level than high-level wrappers, which gives control over architecture and training loops at the cost of more code, and it supplies serving and edge deployment targets.

### TensorFlow Lite · `Library`

An open-source tool for running machine-learning models on mobile and embedded devices. It converts a trained model into a compact, optionally quantisable format, and can dispatch to CPU, GPU or custom ASIC accelerators. Quantisation reduces precision, so accuracy should be re-measured after conversion rather than assumed.

### TensorFlow Serving · `Library`

An open-source utility that serves TensorFlow models in production over HTTP and gRPC, with high scalability and low latency. It supports version hot-swapping, so a newly trained model can be loaded and made live without restarting the server. The serving contract is fixed at export time, making the saved-model signature part of the deployment interface.

### TensorFlow.js · `Library`

An open-source library for building and deploying machine-learning models in JavaScript, training and executing them in the browser or on Node.js. Running inference client-side keeps raw input off the server, which suits privacy-sensitive or low-latency applications. Browser memory and compute ceilings mean larger models are trained elsewhere and only executed here.

### Text Analysis · `Machine Learning`

The steps used to analyze and manipulate textual data in order to extract meaningful information and patterns. In data preparation its job is specifically verifying: validating that the proper groupings are set and that the programming is not overlooking hidden data. Because the input is unstructured, tokenisation and normalisation decisions precede any statistics.

### Threshold Value · `Statistics`

The value used to split data into categories at one internal node of a decision tree, chosen from the candidate cuts on a single feature. It is learned by the split search rather than set by a human, so it reflects the training data rather than domain knowledge. Deep trees produce many thresholds, which is why they overfit.

### Time series forecasting · `Machine Learning`

Predicting future values of a time-ordered series. Validation must be walk-forward rather than a random split, since random cross-validation leaks the future into the past by training on later observations and testing on earlier ones, producing scores that cannot be reproduced in production. The split must respect the arrow of time.

### Timestamps · `Programming`

A timestamp is a representation of a specific moment in time, typically a combination of date and time, used for record-keeping and data tracking. A UNIX timestamp is a numerical value representing the number of seconds elapsed since January 1, 1970, 00:00:00 UTC. APIs return times in both forms, and an epoch number means nothing until a timezone is assumed.

### Timezone-aware datetime · `Programming`

A datetime that carries a UTC offset alongside the date and time, so the instant it denotes is unambiguous. Price history returns a timezone-aware index, printing values such as `2010-06-29 00:00:00-04:00` for one instrument and `2002-02-13 00:00:00-05:00` for another, and `.dt.tz_localize(None)` strips the offset. Mixing aware and naive values raises rather than guessing.

### to_csv() · `Library`

Saves a data frame to a CSV file at a specified path, written as `df.to_csv(<output CSV path>)`. A typical call is `df.to_csv("auto_CLEAN.csv", index=False)`, where `index=False` omits the row numbers rather than writing them as a leading unnamed column. It closes the load-clean-save loop by putting the processed frame back on disk under a new name.

### Token · `Generative AI`

The unit a language model reads and writes: a word, part of a word or a punctuation mark produced by a tokeniser. Everything is priced and limited in tokens — context windows, API cost and generation length — so token counting is a practical design constraint, not a detail.

### Tokenisation · `Generative AI`

Splitting text into the tokens a model consumes, usually with a subword scheme such as byte-pair encoding that keeps common words whole and breaks rare ones into pieces. The choice fixes the vocabulary, the sequence length and the cost of every request.

### Training Set · `Machine Learning`

The subset of data used to train or fit a machine learning model, consisting of input data and the corresponding labelled outputs. In modelling it also serves as the instrument for variable selection and as a gauge to calibrate the model, giving a feasibility verdict on the business question. Performance on these rows measures memory, not generalisation.

### train_test_split() · `Machine Learning`

The scikit-learn utility that divides a dataset into independent training and test partitions, imported as `from sklearn.model_selection import train_test_split` and called as `train_test_split(x_data, y_data, test_size=0.10, random_state=1)`. The features are separated first, typically `y_data = df['target_attribute']` and `x_data = df.drop('target_attribute', axis=1)`, so the target never enters them. A score on training rows measures memory, not generalisation.

### Train/validation/test split · `Machine Learning`

Dividing data into a training set that fits parameters, a validation set that tunes hyperparameters and selects the model, and a test set touched once at the end to estimate generalisation. Reusing the test set for decisions is the most common way a reported score becomes fiction.

### Transactions (databases) · `Database`

A group of statements executed as one atomic unit, so the database either applies all of them or none, with `COMMIT` making the work permanent and `ROLLBACK` discarding it. They are the mechanism that keeps a multi-statement write consistent when something fails partway through. No other language feature protects this, so such writes should be wrapped in one.

### Transfer learning · `Machine Learning`

Starting from a model trained on a large related task and adapting it to a smaller target task, either by using its representations as features or by fine-tuning its weights. It is the standard approach when labelled data for the real problem is scarce, and it only works when the source task is genuinely related.

### Transformer · `Generative AI`

The neural architecture behind modern language models, built from stacked self-attention and feed-forward blocks with no recurrence, so every position attends to every other in parallel. Parallelism is why it could be trained at scale, and attention's quadratic cost in sequence length is why context windows are expensive.

### Transpose, reshape and arange · `Python`

Three core array operations: transposing a multi-dimensional array, `transposed_arr = arr.T`, swaps its axes; reshaping, `reshaped_arr = arr.reshape(2, 3)`, changes its shape without changing its data; and `np.arange(15, dtype=np.int64).reshape(3, 5)` builds values and shape in one expression. The element count must be preserved by a reshape or a `ValueError` follows.

### Trino · `Data Engineering`

A distributed SQL query engine that federates many sources — object storage, relational databases, Kafka — behind one SQL interface without moving the data first. It separates the query layer from the storage layer, which is what makes a lakehouse queryable alongside existing systems.

### True-Positive Rate · `Statistics`

The rate at which the model correctly identifies positive outcomes, computed as `TP / (TP + FN)` and also called sensitivity or recall. It is the y-axis of the ROC curve, whose x-axis is the false-positive rate. Because it moves with the chosen classification threshold, it should be reported alongside the false-positive rate rather than alone.

### try / except / else / finally · `Python`

The four blocks of Python's error handling: `try` attempts a block of code, `except` specifies alternative actions to execute if an error occurs, `else` runs only when no exception occurred, and `finally` runs regardless of whether one was raised. The structure separates the happy path from the handling and guarantees cleanup. Catch specific types: a bare `except:` hides mistakes too.

### t-SNE and UMAP · `Machine Learning`

Two nonlinear dimensionality reduction techniques that place high-dimensional data into a lower-dimensional embedding. t-SNE, t-Distributed Stochastic Neighbor Embedding, visualizes high-dimensional data well, with `n_components` defaulting to `2` and `perplexity` to `30`, balancing local and global structure; it is computationally expensive and prone to overfitting. UMAP approximates the manifold the data lies on. Distances between separated clusters are not meaningful.

### Tuples · `Python`

Ordered and immutable collections of elements, written as comma-separated elements in parentheses `()`. A tuple is the honest type for a fixed record such as a coordinate, a table row or a `(key, value)` pair, because the immutability guarantees the shape cannot drift. That same guarantee makes a tuple usable as a dictionary key.

### Type casting · `Python`

The process of converting one data type to another data type, also called typecasting, type coercion or type conversion. Input arrives as text and models need numbers, so casting is typically the first step of any pipeline. Getting it wrong is the most common runtime error: a cast either raises on unparseable text or silently produces the wrong value.

### TypeScript · `Language`

A superset of JavaScript that adds static typing to the language, catching many type errors before the code runs. It compiles down to ordinary JavaScript, so it runs wherever JavaScript does. Adoption is not free: the type annotations are extra work, and they describe the code rather than the data flowing through it at runtime.

---

## U

*9 terms*

### Union · `SQL`

The combination of two sets that includes both the common and the unique elements from both sets, obtained with the `union()` method or the `|` operator. Because it also deduplicates, it answers the question of every distinct value across several collections in one call. `album_set1.union(album_set2)` returns four elements from two three-element sets that share two.

### Unity Catalog · `Data Governance`

Databricks' unified governance layer for data and AI assets, providing one permission model, lineage and audit trail across workspaces, tables, models and files. Centralising access control is what makes a multi-workspace platform auditable.

### Univariate Analysis · `Machine Learning`

Statistics computed on one variable at a time, applied first and per column, with the histogram as its visual half. Looking at each column in isolation establishes range, central tendency, spread and the shape of the distribution before any relationship is examined. It cannot show interactions, so it is a starting point rather than a full description of the data.

### Unstructured Data · `Data Engineering`

Data that does not have a predefined structure or format, such as text, images, audio and video, and requires specialized techniques for analysis. Lacking columns and types, it cannot be queried directly and must first be converted into features. This is why text analysis is part of the methodology rather than an optional extra.

### Unsupervised learning · `Machine Learning`

Learning in which the data is not labelled and the model identifies patterns without external help, with clustering and anomaly detection as the standard examples. Because no ground truth exists, there is no accuracy score to appeal to, so results are judged by internal measures and domain plausibility. It often explores data before a supervised task is formulated.

### UPDATE … SET … WHERE · `SQL`

The statement that changes data already in place, as in `UPDATE Instructor SET lastname = "vioElVideo", firstname = "JuanWong" WHERE ins_id = 2;`. `SET` takes a comma-separated list of `column = value` assignments, every row matching the predicate is updated, and assignments may reference other columns of the same row. Omitting the `WHERE` updates every row.

### Uplift modelling · `Machine Learning`

Predicting the change an intervention causes in a customer rather than the outcome itself. A model trained across treated and control groups estimates who actually responds, so budget goes to the persuadable instead of to customers who would have converted anyway. It is the production form of heterogeneous treatment effects, and the usual mistake is validation: ranking by predicted outcome rather than predicted uplift quietly rebuilds the targeting you already had.

### URL · `Web & APIs`

A uniform resource locator is the most popular way to find resources on the web, divided into three parts: the scheme, the internet address or base URL, and the route. The scheme selects the protocol, the base address names the host, and the route identifies the particular resource on it. Query strings and fragments sit outside that three-part description.

### urllib · `Web & APIs`

The Python library used for working with URLs and making HTTP requests, including functions for fetching web content, handling cookies and more. Alongside it, `httplib` provides functions and classes to send and handle HTTP and HTTPS requests. Both are the standard-library layer beneath higher-level clients such as `requests`, and recognising their frames in a traceback localises a failed fetch.

---

## V

*16 terms*

### Vanity metric · `Analytics & BI`

A number that looks impressive and grows on its own — total sign-ups, page views, cumulative downloads — without indicating whether anything valuable happened. It is a metric that cannot fall, which is exactly why it cannot guide a decision.

### Variables · `Python`

Variables are containers for storing data values, implemented as a name bound to a value and created by assignment. The name is the only handle you have on a value, and the distinction between rebinding a name and mutating the object it points to is behind most beginner bugs. A binding can be replaced at any time.

### Variational Autoencoders (VAEs) · `Generative AI`

A generative architecture that pairs an encoder mapping data to a latent distribution with a decoder that reconstructs data from latent codes sampled from it. Training maximizes the ELBO, balancing reconstruction quality against the KL divergence between the learned latent distribution and a prior. The probabilistic latent space allows new samples to be generated, at the cost of blurrier reconstructions.

### Variety · `Data Engineering`

The diversity of data types, spanning structured and unstructured forms such as text, images and video, which poses data-management challenges. It is one of the pressures that distinguishes modern data work from purely tabular processing, since each type needs its own storage and parsing strategy. Volume and velocity say how much and how fast; variety says how many shapes.

### Vector addition and subtraction · `Statistics`

Vector addition in Python involves adding corresponding elements of two or more vectors, producing a new vector with the sum of their components, and subtraction replaces the addition sign with a negative sign. The operation is widely used, and representing it with line segments or arrows is useful. Both vectors must share the same shape.

### Vector database · `Generative AI`

A store built to hold embeddings and answer nearest-neighbour queries at scale, using approximate indexes such as HNSW or IVF to trade a little recall for large gains in speed. It is what makes retrieving the few relevant passages out of millions fast enough to put in front of a model.

### Vector search · `Generative AI`

Finding the items whose embeddings are closest to a query embedding, usually by cosine similarity or Euclidean distance. It retrieves by meaning rather than by keyword overlap, so a question phrased in new words can still find the passage that answers it.

### Vegas · `Library`

The Scala library for statistical data visualizations, the visualization companion of Spark's Scala API. It fills the role that Matplotlib and Seaborn fill for Python, letting a Scala application chart data frames without leaving the language. It is declarative, so charts are described as specifications rather than drawn imperatively.

### Velocity · `Data Engineering`

The speed at which data accumulates and is generated, often in real time or near real time, which drives the need for rapid processing and analytics. It is one of the defining dimensions of big data, since a pipeline slower than its input falls permanently behind. Streaming architectures exist mainly to answer this pressure.

### Venn diagram · `Statistics`

A graphical representation that uses overlapping circles to illustrate the relationships and commonalities between sets or groups of items. It is the natural visual for the set algebra: the union is both circles, the intersection is the overlap, and the difference is one crescent. Beyond two or three sets the picture stops being readable.

### Veracity · `Data Engineering`

The quality and accuracy of data, understood as conformance to fact, consistency, completeness and freedom from ambiguity. It determines the reliability and trustworthiness of anything computed from that data. It is the dimension hardest to fix downstream, because errors of meaning cannot be repaired by scaling infrastructure.

### Version control · `Tool`

The practice of tracking changes to documents, and specifically to code, so that any revision can be inspected or restored. It is the precondition for reproducibility, collaboration and recovery, since without a history there is no way to say what produced a given result or to undo a mistake. Branching and merging make it a coordination mechanism.

### Views · `SQL`

A named stored query that behaves like a table: it holds no data of its own, so selecting from it runs the underlying query and always shows current base-table rows. Restricting a view's columns and rows is a standard way to expose part of a table, and it is dropped with `DROP VIEW`.

### Visual Studio Code (VS Code) · `Tool`

A free, open-source code editor for debugging and running tasks on Linux, Windows and macOS. With its Jupyter extension it becomes one of the popular environments for creating and modifying notebooks locally, blending plain editing with interactive execution. Its power comes from extensions, so a configured setup is not automatically reproducible on another machine.

### Visualization · `Visualization`

Representing data visually in order to gain insights into its content and quality. It is the visual half of the data understanding stage, paired with statistics at every stage because each catches what the other misses: summary measures hide distributions that a plot reveals. Charts are also how findings are communicated, so the skill serves both analysis and delivery.

### Volume · `Data Engineering`

The scale of data generated and stored, driven by increased numbers of data sources, higher-resolution sensors and scalable infrastructure. It is one of the dimensions that decides whether a problem fits on one machine or needs distributed processing. Growing volume is answered by scalable storage and parallel compute rather than by sampling alone.

---

## W

*12 terms*

### Waffle chart · `Visualization`

A grid of small squares in which each square stands for a fixed quantity, so a proportion is read by counting cells rather than estimating an angle or a length. It is an effective alternative to a pie chart for a small number of categories, and it is usually built by hand from a scatter of square markers.

### Watermark · `Data Engineering`

A moving threshold in stream processing that declares how late an event may still arrive and be counted, letting the engine know when a window's result is complete. It is the explicit trade between correctness and latency in any streaming aggregation.

### Web scraping · `Web & APIs`

Web scraping, also known as web harvesting or web data extraction, is the process of extracting information from websites or web pages through automated retrieval. It is used for data analysis, mining, price comparison and content aggregation. Scrapers are brittle because page structure changes without notice, and they must respect terms of service and `robots.txt` to avoid being blocked.

### Web service · `Web & APIs`

Web services in Python are software components that allow applications to communicate over the internet by sending and receiving data in a standardized format, typically using protocols like HTTP or XML. A service is the server side of the API relationship, the thing your request is answered by, which is why its contract matters more than its implementation.

### Weights & Biases · `MLOps`

A hosted experiment-tracking and model-management platform: runs log parameters, metrics, system usage and artifacts, with dashboards for comparing experiments and a registry for model promotion. It is widely used where MLflow's self-hosted model does not fit the team.

### Weka · `Library`

A data-mining toolkit built with Java, providing a library and graphical interfaces, Explorer, Experimenter and KnowledgeFlow, that cover classification, regression, clustering, association rules and attribute selection. The GUI makes it possible to run a full workflow without writing code, which is useful for learning and quick comparison. It is oriented toward experimentation on modest datasets rather than production deployment.

### WHERE · `SQL`

The clause that filters rows with a Boolean predicate evaluated per row: rows for which the predicate is not true are absent from a read and untouched by a write. It is the only safety mechanism on `UPDATE` and `DELETE`, so omitting it affects the whole table. Typical forms include `WHERE Writer="James Cameron"` and `WHERE ins_id = 2`.

### while loop · `Python`

A while loop in Python repeatedly executes a block of code as long as a specified condition is true. It is the loop for situations where no iterable exists to walk, such as draining a queue, retrying an operation or filtering a shrinking collection. Because the condition is checked only at the top, it must eventually become false.

### Windowing · `Data Engineering`

Grouping an unbounded stream into bounded chunks for aggregation — tumbling windows that do not overlap, sliding windows that do, and session windows that close after inactivity. The window type decides what a streaming aggregate can mean.

### Word clouds · `Visualization`

Word clouds, also called tag clouds, work in a simple way: the more a specific word appears in a body of textual data, such as a speech, blog post or database, the bigger and bolder it appears. They give a concise visual overview of the most common words in a text. Frequent words need not be the important ones.

### Working directory · `Python`

In Git, the files and subdirectories you actually edit — the first of its three areas, alongside the staging area and the repository. More generally, the working directory of a running program is the folder that relative paths resolve against, which is why a script can work in one shell and fail in another.

### Writing to a file · `Python`

The `write()` method stores a string and returns the number of characters written, which is why `"This is line A"` reports `14` and `"This is line A\n"` reports `15`: the newline is a character and counts. Appending means adding something to the end of an object, typically data to a file or list elements. Text written is a string.

---

## X

*1 term*

### XGBoost · `Machine Learning`

A highly optimised gradient-boosting implementation that adds regularisation, handles missing values natively, supports parallel tree construction and stops early on a validation set. It has been the default winner of tabular competitions for years, and it remains the baseline a neural approach must beat.

---

## Y

*1 term*

### yfinance · `Library`

The Python client for Yahoo Finance market data, where `yf.Ticker(symbol)` is the handle to a single instrument and `history()` returns its price series. It is the API route to price history while other figures, such as revenue, may need scraping, and not all stock data is available via the API. Returned figures should be checked before being relied on.

---

## Z

*1 term*

### Zero-shot prompting · `Generative AI`

Asking a model to perform a task with instructions alone and no worked examples, relying on what pretraining already taught it. It is the fastest thing to try and the first to fail on tasks with an unusual output convention.
