[![Apache License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![dbt logo and version](https://img.shields.io/static/v1?logo=dbt&label=dbt-version&message=1.x&color=orange)

# Medicare SAF Claims Connector

## 🧰 What does this project do?

This connector transforms raw Medicare SAF claims data into the Tuva Claims Input Layer which enables you to run most of the other components of the Tuva Project with very little effort.
For a detailed overview of what the project does and how it works, check out our [Knowledge Base](https://thetuvaproject.com/docs/getting-started). 
For information on data models and to view the entire DAG check out our dbt [Docs](https://tuva-health.github.io/medicare_saf_connector/#!/overview?g_v=1).

## 🔌 Database Support

- BigQuery
- Redshift
- Snowflake

## ✅ How to get started

### Pre-requisites
1. You have Medicare SAF claims data loaded into a data warehouse.
2. You have [dbt](https://www.getdbt.com/) installed and configured (i.e. connected to your data warehouse).

[Here](https://docs.getdbt.com/dbt-cli/installation) are instructions for installing dbt.

### Getting Started
Complete the following steps to configure the package to run in your environment.

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repo to your local machine or environment.
2. Update the dbt_project.yml file to use the dbt profile connected to your data warehouse.
3. Run `dbt build` command while specifying the specific database and schema locations you want to read/write data fromt/to: 

    > dbt build --vars '{key: value, input_database: medicare, input_schema: saf, output_database: tuva, output_schema: claims_input}'

Note: The source data table names need to match the table names in [sources.yml](models/sources.yml).  These table names match the [Medicare SAF data dictionary](https://www.cms.gov/Research-Statistics-Data-and-Systems/Files-for-Order/LimitedDataSets/StandardAnalyticalFiles).  If you rename any tables make sure you:
- Update table names in sources.yml
- Update table name in medical_claim and eligibility jinja function

## 🙋🏻‍♀️ **How is this project maintained and can I contribute?**

### Project Maintenance

The Tuva Project team maintaining this project **only** maintains the latest version of the project. 
We highly recommend you stay consistent with the latest version.

### Contributions

Have an opinion on the mappings? Notice any bugs when installing and running the project?
If so, we highly encourage and welcome feedback!  While we work on a formal process in Github, we can be easily reached on our Slack community.

## 🤝 Community

Join our growing community of healthcare data practitioners on [Slack](https://join.slack.com/t/thetuvaproject/shared_invite/zt-16iz61187-G522Mc2WGA2mHF57e0il0Q)!
