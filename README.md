# Awesome Automation Workflow Datasets and Templates

This document lists public datasets and template libraries for collecting large numbers of automation workflows. Combining the sources below can yield well over 5,000 workflows spanning business automation, integration, and data engineering.

## Integration and Business Automation Platforms

### IFTTT
- Over 320,000 user-created applets shared publicly by 2017.
- Open dataset (Nov 2016 – May 2017) ~200 GB in JSON, with metadata for each applet (title, description, trigger, action, usage count).
- Covers IoT, social media, smart home and more; each applet is a trigger→action script.

### Zapier
- SaaS platform with 8,000+ app integrations.
- Thousands of ready-made “Zap” templates such as "Save new Gmail attachments to Google Drive" or "Add Typeform responses to Google Sheets."
- Templates can be discovered via the Templates gallery and app directories, though no bulk download is offered.

### n8n
- Open-source automation tool with ~4,593 templates in the official library.
- Community-maintained GitHub collections offer 2,000+ additional workflows.
- Workflows are stored as JSON, each defining nodes and connections; credentials are shared as placeholders.

### Make (formerly Integromat)
- Template gallery with over 7,500 ready-made automation scenarios.
- Scenarios are shared as JSON "blueprint" files importable into Make.
- Covers marketing, sales, IT, and other domains.

### Pipedream
- Cloud integration platform supporting serverless steps and code.
- Public Templates Gallery with hundreds of workflows, each accessible via unique URL.
- Templates can be exported as JSON; common uses include scheduling emails, syncing data, and sending Slack notifications.

### StackStorm
- Open-source event-driven automation platform for DevOps and SREs.
- StackStorm Exchange hosts 160+ integration packs with over 6,000 actions.

## Data Engineering and ETL Workflow Tools

### Apache NiFi
- Open-source dataflow automation tool.
- Flows can be exported as XML templates.
- Repositories like Hortonworks' NiFi Templates Gallery and AI4EU’s collection provide numerous example templates for processors such as SQL, S3, MQTT, and APIs.

### Apache Airflow
- Python-based workflow orchestrator where each DAG is a `.py` script.
- Example DAGs are available via Astronomer’s Registry, Clairvoyant’s maintenance DAGs, and many community GitHub repositories.
- DAGs demonstrate ETL patterns, API queries, data warehouse loads, ML pipelines, etc.

### dbt (Data Build Tool)
- Defines analytics transformations using SQL models and YAML configs.
- Hundreds of community packages listed on dbt Hub and many open-source dbt projects exist (e.g., the `jaffle_shop` demo).
- Aggregating models from multiple projects can easily exceed thousands of workflow definitions.

## Additional Resources
- [dariubs/awesome-workflow-automation](https://github.com/dariubs/awesome-workflow-automation) – curated list of workflow automation software, engines, and tools.
- [rpabotsworld/awesome-rpa](https://github.com/rpabotsworld/awesome-rpa) – robotic process automation tools, frameworks, and resources.
- [networktocode/awesome-network-automation](https://github.com/networktocode/awesome-network-automation) – network automation resources and frameworks.
- [atinfo/awesome-test-automation](https://github.com/atinfo/awesome-test-automation) – test automation frameworks and libraries.
- [correlatedsecurity/Awesome-SOAR](https://github.com/correlatedsecurity/Awesome-SOAR) – security orchestration, automation, and response tools.
- [EPMatt/awesome-ha-blueprints](https://github.com/EPMatt/awesome-ha-blueprints) – community-driven collection of Home Assistant automation blueprints.
