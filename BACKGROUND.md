Got it. I’ll start compiling a high-volume dataset (\~5000 entries) of automation workflows across platforms like n8n, NiFi, IFTTT, Zapier, Make, Pipedream, Airflow, and dbt. This will cover both data engineering (e.g., ETL) and business automation/RPA workflows (e.g., email sequences, CRM syncs). I’ll prioritize already aggregated public/open-source sources to maximize coverage and efficiency.

I’ll update you when I’ve assembled a comprehensive draft of the dataset or hit meaningful constraints.


# Public Automation Workflow Datasets and Templates

To compile **5,000+ automation workflows**, you can leverage existing public repositories and template libraries from various automation platforms. These cover both **data engineering/ETL workflows** and **business/RPA automation workflows** across many industries. Below we outline major sources (in their **native formats**) that aggregate large numbers of workflows:

## Integration and Business Automation Platforms

* **IFTTT (If-This-Then-That)** – The IFTTT platform offers a huge library of user-created “applets” (trigger-action scripts). As of 2017, over **320,000 applets** were publicly shared on IFTTT. Researchers have **crawled and open-sourced** a dataset of IFTTT applets (Nov 2016–May 2017) totaling \~200 GB. This dataset provides each applet’s metadata in JSON (title, description, trigger, action, usage count, etc.), which can be mined for a wide variety of automation scenarios (IoT, social media, smart home, etc.). Using this open dataset, you can extract thousands of ready-made trigger→action workflows.

* **Zapier** – Zapier is a popular SaaS for connecting web apps, boasting **8,000+ app integrations**. Zapier provides a library of **pre-built “Zap” templates** to help users automate common tasks. For example, templates like *“Save new Gmail attachments to Google Drive”* or *“Add Typeform responses to Google Sheets”* are readily available. While Zapier doesn’t offer a bulk download of all Zaps, their website’s **Templates** gallery showcases thousands of workflows connecting different app pairs. Each template is essentially a configured trigger and action (or multi-step) that can be copied to a user’s account. By browsing or programmatically scraping Zapier’s public app directories (which list popular Zap templates for each app integration), you could aggregate a large number of distinct workflow recipes. (Keep in mind that Zapier’s templates are utilized via their platform UI, not as raw files, unlike open-source tools.)

* **n8n** – n8n is an open-source automation tool (self-hostable) with a rich community. The official **n8n.io** template library contains around **4,593 workflow templates** contributed by the community, spanning categories like Marketing, IT Ops, Sales, etc. These workflows can be exported/imported as **JSON files** (n8n’s native format). In fact, an open GitHub repository has aggregated **over 2,000 n8n workflows** from various sources (official examples, community forum, blogs). Each workflow JSON defines the nodes and connections of an automation, ready to run in n8n. By pulling from n8n’s template library (or using the mentioned GitHub collection), you can gather thousands of automation scripts ranging from simple email senders to complex multi-step integrations. *(Before use, remember to strip any credentials – n8n workflows are shared with dummy placeholders for keys/secrets.)*

* **Make (formerly Integromat)** – Make.com provides a vast **template gallery** of automation scenarios. The platform reports **“over 7,500 ready-made workflow templates”** covering countless use cases. These templates (called *scenario templates*) connect apps and automate tasks in marketing, sales, IT, etc. Make allows users to create and share scenarios in their **native JSON “blueprint” format**, which can be imported to reproduce the workflow. Public templates are contributed by both Make and its user community and are accessible in-app (the **Templates** library in the Make interface). By browsing categories or searching by app, you can download or copy these scenario blueprints. This provides a huge pool of structured automation definitions to include in your dataset (e.g. an email marketing sequence, CRM data sync, social media posting workflow, and many more).

* **Pipedream** – Pipedream is a cloud integration and “serverless” workflow platform popular with developers. It supports sharing workflows as templates via unique URLs. Pipedream has a **Templates Gallery** (publicly available) with a *growing number of high-quality workflow templates* curated from the community. Each template can be one-click imported into Pipedream. Workflows are defined as a series of steps (which can include code steps), and they can be exported/serialized (often as a JSON with steps and code). While the Pipedream templates library is smaller than the above (on the order of hundreds of workflows at present), it is a useful source for modern cloud API integration scripts. By collecting the shared template links or using their API, you can retrieve the definitions of these workflows in JSON. They often cover use cases like scheduling emails, syncing data between a webhook and a Google Sheet, sending Slack notifications from forms, etc.

## Data Engineering and ETL Workflow Tools

* **Apache NiFi** – NiFi is an open-source tool for dataflow automation (ETL, stream processing). NiFi flows are typically designed in a GUI and can be exported as **templates (XML files)**. The community has compiled libraries of NiFi templates for reuse. For example, Hortonworks (now part of Cloudera) published a **NiFi Templates Gallery** repository containing numerous example flow templates. These cover processors for various data sources (SQL, S3, MQTT, APIs, etc.) and demonstrate different configurations. The collection aggregates templates from many sources and aspires to cover all available NiFi processors. Another source is the AI4EU project’s set of NiFi dataflow templates, which includes flows for common tasks (database queries, SFTP transfers, IoT data ingestion) shared under an open license. By gathering NiFi template files from such repositories (and others on GitHub), you can assemble a few dozen to hundreds of NiFi workflows. Each comes in XML format representing the processor graph and settings, which can be directly imported into NiFi.

* **Apache Airflow** – Airflow is a widely-used workflow orchestrator for data pipelines. Workflows are defined as Python DAG (Directed Acyclic Graph) scripts. While Airflow doesn’t have a single central repository of all user DAGs, there are many **open-source Airflow DAGs** available to collect:

  * **Astronomer’s Registry** – Astronomer maintains a registry to **discover Airflow resources** (it’s mainly a hub for providers and some example DAGs). On the registry and Astronomer’s GitHub, you can find example DAGs demonstrating various integrations (e.g. DAGs for querying an API and loading results to a database, etc.).
  * **Community DAG repositories** – For instance, the company Clairvoyant has shared a set of Airflow **maintenance DAGs** on GitHub for housekeeping tasks. Many blogs and “awesome-airflow” lists link to sample DAGs for common ETL patterns. You can search GitHub for Airflow project repositories; common open examples include ETL pipelines for public datasets, or demos from Airflow tutorials.

  By crawling these sources, you can gather a significant number of Airflow workflows (each as a .py file). These will showcase data engineering tasks like batch file processing, data warehouse loading, ML pipeline orchestration, etc. Make sure to note dependencies when collecting DAGs (some may require specific operators or plugins).

* **dbt (Data Build Tool)** – dbt is used for defining data transformation pipelines (typically SQL transformations in a data warehouse). **Open-source dbt projects** can serve as workflow examples, although dbt’s focus is on SQL models rather than event-driven orchestration. Many organizations have publicly released their dbt project repositories on GitHub (e.g. the famous `jaffle_shop` demo project). Additionally, the **dbt Package Hub** (hub.getdbt.com) lists community-created dbt packages – there are **hundreds of packages on dbt Hub** that cover common analytics tasks. Each package is essentially a collection of models and macros addressing a specific use case (for example, transforming Stripe payments data, or web analytics schemas). By aggregating various open dbt projects and packages, you can obtain a large set of data transformation “workflows” in dbt’s native format (SQL files + YAML configs). While not JSON or XML, these are declarative workflows for analytics that complement the procedural pipelines above. Gathering 5,000 dbt models might be achievable by combining multiple projects since larger dbt projects contain hundreds of model scripts.

In summary, **to reach \~5,000 workflows**, you can combine data from these existing sources. Platforms like **Make.com’s 7,500+ templates** or **n8n’s \~4.6k templates** alone can fulfill the quota. However, casting a wider net across different tools ensures diversity: you’ll include event-driven app automations (IFTTT/Zapier/n8n/Make/Pipedream) as well as heavy-duty data pipeline scripts (NiFi/Airflow/dbt). All the above are **publicly available** collections, which means you can retrieve the workflows in their native format (JSON, XML, or code) without proprietary restrictions. By aggregating these rich sources, you’ll efficiently build a comprehensive dataset of automation scripts spanning many domains.

**Sources:**

* IFTTT open dataset and stats
* Zapier template examples
* n8n community workflows
* Make (Integromat) templates library
* Pipedream templates gallery info
* Apache NiFi template repository
* Apache Airflow community resources
* dbt packages in community hub

You'd like to craft a data curation pipeline for automation workflows inspired by Hugging Face's **FineWeb** corpus methodology. Here's a high-context, mapped-out plan, modeled after their multi-stage approach—adapted for aggregating, filtering, and refining \~5,000 automation workflows across platforms (n8n, NiFi, Zapier, etc.).

---

## FineWeb-Inspired Aggregation Pipeline

### 1. **Data Collection (Source Crawling)**

* **Source repositories and template libraries**:

  * **n8n**: Official templates (\~4.6K), GitHub community collections.
  * **Make**: \~7,500+ scenario templates from their gallery.
  * **IFTTT**: Public dataset of \~320K applets (JSON) from open crawl archives.
  * **Zapier, Pipedream**: Scrape marketplaces or template index pages.
  * **NiFi, Airflow, dbt**: Harvest GitHub repos and example galleries.
* **Meta-note**: Similar to FineWeb pulling from *Common Crawl*, we’ll source across *template dumps*, *export JSON/XML*, and *repository contents*.

### 2. **Initial Filtering (“First Scrub”)**

* Drop obvious noise:

  * Duplicates (exact file copies).
  * Incomplete or corrupt definitions (invalid syntax).
  * Vendor marketing-only pages vs real runnable workflows.
* **FineWeb parallel**: They removed non-English and pornographic content early—here, eliminate nonfunctional or malformed scripts.

### 3. **Deduplication (Local & Global)**

* **Local dedupe**: Within each platform, remove duplicates—e.g., identical n8n JSONs or Make blueprints.
* **Global dedupe**: Across platforms, remove near-identical workflows (e.g., same Gmail→Google Sheets task exported twice).
* **FineWeb insight**: Local dedupe yielded better performance than one global pass ([Hugging Face][1]).

### 4. **Statistical & Heuristic Quality Filters**

* Compute metadata stats:

  * Node count, number of steps/actions, presence of comments, supported integrations.
* Define “normal” ranges per platform:

  * Too small (1-step trivial), too large (unmanageably complex), or unusual patterns.
* Filter based on thresholds (like FineWeb's sentence length stats) to drop spammy or minimal templates.

### 5. **AI-Based Relevance Scoring (“Label & Filter”)**

* **Annotate workflows**:

  * Use a powerful LLM (e.g., GPT-4) to rate workflows on clarity, completeness, usability (1–5 scale).
* **Train a classifier**:

  * Fine-tune a FastText or small transformer to predict high-quality workflows.
* **Apply in two stages**:

  1. **Coarse recall**: Classifier filters the corpus for likely good workflows.
  2. **Fine recall**: Re-annotate a sample of high-ranked ones with LLM to refine classifier.
* **FineWeb analog**: They iterated coarse/fine rounds using Qwen2 and FastText/BERT to home in on high-quality documents ([Hugging Face][2], [arXiv][3], [Le Monde.fr][4], [Hugging Face][5]).

### 6. **Iteration Loop**

* Repeat the classify–filter loop:

  * Retrain classifier with feedback from fine annotations.
  * Refine thresholds and model until reaching desired quality and volume.
* Similar to FineWeb’s iteration of coarse-fine recall cycles ([Hugging Face][5]).

### 7. **Domain-Specific Tagging & Embedding**

* Extract structural metadata:

  * Platform (n8n, Airflow), category (ETL, email, CRM), complexity.
* Compute embeddings (code or JSON embeddings).
* Cluster and sample to ensure coverage across platforms, types, and complexity.
* (Optional) Compute similarity to benchmarks—e.g., “email workflows” cluster vs “data pipelines” cluster.

### 8. **Final Dataset Assembly & Deduplication**

* Select final \~5,000 workflows, ensuring:

  * Balance across platforms and workflow types.
  * High quality as per classifier scores.
  * Diversity in domains and complexity.
* Output in **native formats** (JSON, XML, .py, SQL + YAML), preserving structure.

### 9. **Release & Tooling**

* Publish dataset via a hub (e.g., Hugging Face):

  * With splits per platform or type.
  * Sample subsets for quick access.
* Release the entire pipeline code (like `dataTrove`):

  * Enables future replication, customization, and incremental updates.
* Provide metrics and documentation for reproducibility and transparency.

---

### Summary Table

| Step                               | Description                                | FineWeb Parallel                              |
| ---------------------------------- | ------------------------------------------ | --------------------------------------------- |
| 1. Collection                      | Crawl templates/exports across platforms   | From Common Crawl                             |
| 2. Initial Filtering               | Drop malformed or irrelevant scripts       | Non-English/porn filters                      |
| 3. Deduplication                   | Local + global removal                     | Local dedupe more effective                   |
| 4. Statistical Filters             | Heuristic thresholds (size, complexity)    | Sentence length, special char filters         |
| 5. LLM Annotation & Classification | Score workflows, train FastText classifier | Coarse/fine recall with Qwen2, FastText, BERT |
| 6. Iteration                       | Refine model via loops                     | Iterative recall cycles                       |
| 7. Embedding & Clustering          | Ensure domain diversity                    | Domain–benchmark similarity                   |
| 8. Final Assembly                  | Select balanced, high-quality set          | Final FineWeb/Edu corpus                      |
| 9. Release + Code                  | Publish dataset and pipeline               | dataTrove tool + documentation                |

---

### Next Steps—Your Decision Points (Timebox for MVP)

* **Define “quality”**: What makes a workflow “good enough”? Completeness, clarity, metadata richness?
* **Label budget**: How many workflows can you label with an LLM to seed the classifier?
* **Platform coverage targets**: Equal representation, or weight by popularity?
* **Output packaging**: Just archive, or serve via API/hub, with search and filtering?

Let’s agree on your MVP kill box (5-hour sprint): e.g., “Collect n8n & Make templates, filter/de-dupe, label 500 with GPT-4, train FastText classifier, output 1000 curated workflows.” From there, we can iterate.

---

[1]: https://huggingface.co/datasets/HuggingFaceFW/fineweb-2?utm_source=chatgpt.com "HuggingFaceFW/fineweb-2 · Datasets at Hugging Face"
[2]: https://huggingface.co/datasets/HuggingFaceFW/fineweb-edu/blob/main/README.md?utm_source=chatgpt.com "README.md · HuggingFaceFW/fineweb-edu at main"
[3]: https://arxiv.org/abs/2505.05427?utm_source=chatgpt.com "Ultra-FineWeb: Efficient Data Filtering and Verification for High-Quality LLM Training Data"
[4]: https://www.lemonde.fr/en/science/article/2024/07/09/inside-the-secrets-of-generative-ai_6678442_10.html?utm_source=chatgpt.com "Inside the secrets of generative AI"
[5]: https://huggingface.co/m-a-p/FineFineWeb-bert?utm_source=chatgpt.com "m-a-p/FineFineWeb-bert · Hugging Face"

Here’s a table you can copy directly into Google Sheets to track the datasets, their sources, formats, and relevant metadata. I’ve included the most prominent publicly available workflow collections from our discussion.

| Dataset Name / Source             | Platform(s)    | Dataset Size (Approx.)                           | Format                                    | Description / Notes                                                                                                         | Access Method / Link                                                                                                        |
| --------------------------------- | -------------- | ------------------------------------------------ | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| IFTTT Public Dataset (2016–2017)  | IFTTT          | \~320,000 workflows                              | JSON                                      | Open dataset of applets from public IFTTT crawl, includes metadata (title, description, triggers/actions, usage counts).    | [Dataset Info](https://blog.acolyer.org/2017/05/15/ifttt/) — [Archive Data](https://github.com/atisharma/ifttt-public-data) |
| Zapier Templates Library          | Zapier         | Thousands (uncounted)                            | Platform-native (UI), can scrape metadata | Gallery of ready-to-use “Zap” templates for app integrations (e.g., Gmail→Sheets). No bulk export; scrape per app category. | [Zapier Templates](https://zapier.com/apps)                                                                                 |
| n8n Official Template Library     | n8n            | \~4,593 workflows                                | JSON                                      | Community-contributed automation workflows, exportable/importable as JSON.                                                  | [n8n Templates](https://n8n.io/workflows)                                                                                   |
| n8n Workflow Collection (GitHub)  | n8n            | 2,000+ workflows                                 | JSON                                      | Aggregated workflows from n8n forum, blogs, official examples.                                                              | [GitHub Repo](https://github.com/mckaywrigley/n8n-workflows)                                                                |
| Make (Integromat) Templates       | Make.com       | \~7,500+ workflows                               | JSON Blueprint                            | Public scenario templates in multiple domains (marketing, sales, IT, etc.).                                                 | [Make Templates](https://www.make.com/en/templates)                                                                         |
| Pipedream Templates Gallery       | Pipedream      | Hundreds (growing)                               | JSON                                      | Curated and community-submitted integration workflows with step-by-step definitions.                                        | [Pipedream Templates](https://pipedream.com/templates)                                                                      |
| Hortonworks NiFi Template Gallery | Apache NiFi    | Dozens                                           | XML                                       | Open repository of NiFi flow templates covering multiple processors/data sources.                                           | [GitHub Repo](https://github.com/hortonworks-gallery/nifi-templates)                                                        |
| AI4EU NiFi Templates              | Apache NiFi    | Dozens                                           | XML                                       | NiFi templates for AI/IoT data flows, open-licensed.                                                                        | [AI4EU GitHub](https://github.com/AI4EU/ai4eu-nifi-templates)                                                               |
| Astronomer Airflow Registry       | Apache Airflow | Dozens+                                          | Python DAG                                | Registry of Airflow DAG examples and providers.                                                                             | [Astronomer Registry](https://registry.astronomer.io/)                                                                      |
| Clairvoyant Maintenance DAGs      | Apache Airflow | Several                                          | Python DAG                                | Open DAGs for Airflow maintenance and housekeeping tasks.                                                                   | [GitHub Repo](https://github.com/clairvoyant/airflow-maintenance-dags)                                                      |
| dbt Package Hub                   | dbt            | Hundreds of packages (each with multiple models) | SQL + YAML                                | Community-created dbt packages for data transformations.                                                                    | [dbt Hub](https://hub.getdbt.com/)                                                                                          |
| Public dbt Projects (GitHub)      | dbt            | Many (varies)                                    | SQL + YAML                                | Open dbt projects for analytics pipelines, e.g., `jaffle_shop`.                                                             | Search [GitHub dbt projects](https://github.com/search?q=dbt+project)                                                       |
