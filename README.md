# Some Practical Research Ideas in Data Management for Machine Learning

I work in data management for ML systems. This is an emerging but broad field. This is a list of proposed abstracts I'd love to work on, if I had the time. If you would like to contribute / add an abstract, please make a PR and we can "workshop" the abstract together before merging to the main branch.

If you want to work on one of these ideas, please steal them! But please email me so I can get excited :)

## More Concrete Ideas

### Debugging Feature Generation Workflows via Lineage Visualizations

Modern-day ML systems are challenging to debug due to complex data transformations that occur before the model is even trained. Existing work tracks lineage and inspects data flow for practitioners to look at during the debugging phase (e.g., [Grafberger et al.](http://cidrdb.org/cidr2021/papers/cidr2021_paper27.pdf), [Rezig et al.](http://da.qcri.org/ntang/pubs/cidr20dagger.pdf)). These solutions may work well when practitioners are familiar with the pipeline's architecture and data transformations, but many times practitioners need to debug pipelines that they may not have written. In this work, we introduce a visualization tool to help practitioners understand, at a high level, transformations in feature generation workflows. We adapt the concept of "data tweening," or incremental visualizations of data transformations ([Khan et al.](http://www.vldb.org/pvldb/vol10/p661-khan.pdf)), to debugging ML feature generation by (1) identifying "problematic" subsets of data, (2) isolating top features for models, (3) reducing dimensionality by generating summaries of features, and (4) showing tweening visualizations to the end user. 

Tags: HCI, databases

### Stop Dashboardizing Every Metric Possible: Minimal Metric Sets to Retrain Models

Current dashboards to understand ML performance are littered with thousands of charts visualizing any distance metric between features and outputs. These charts can tell conflicting stories (e.g., one feature distribution "significantly" changed but another one didn't), leading to confusion about when to retrain ML models. In this paper, we conduct empirical studies on "real-world" ML pipelines and propose a framework for constructing a "minimal" set of metrics to monitor.

Tags: HCI

## Half-Baked Ideas

### But _when_ did the Distribution Change?

Current methods to determine whether a dataset has experienced "distribution shift" involve partitioning the dataset into predefined static subsets and computing some distance metrics between these subsets. A simple extension to the streaming ML setting (i.e., where predictions are made over hypothetically infinite streams of data) involves diffing windows of live predictions with each other or the training set. However, it is unclear how large these windows should be or how much these windows should overlap. In this work, we investigate... (partition stream with some learned critera and see how these partitions change over time?) We demonstrate our open-source library of metric functions that accept a stream of data and return a "consistency score" for any time step.

Tags: Databases, ML

## Clippy for Computational Notebooks

Computational notebooks are widely used for exploratory data analysis (e.g., to create plots and visualizations). Sometimes users do not know exactly what to compute or visualize. In this work, we introduce an "assistant" for computational notebooks, modeled after Clippy from Microsoft Office. Users interact with the assistant via a natural language interface and can issue commands like, "update plot font to SF UI" or "train a logistic regression model on the dataframe."

Tags: HCI, PL, AI
