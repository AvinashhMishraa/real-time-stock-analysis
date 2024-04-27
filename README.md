<br>

![Python](https://a11ybadges.com/badge?logo=python) &nbsp; ![pandas](https://a11ybadges.com/badge?logo=pandas) &nbsp; ![Snowflake](https://a11ybadges.com/badge?logo=snowflake) &nbsp; ![Streamlit](https://a11ybadges.com/badge?logo=streamlit) &nbsp; ![Plotly](https://a11ybadges.com/badge?logo=plotly)

---

<div style="padding: 10px; background-color: yellow">

# Real Time Stock Analysis

</div>

<br>

# 1. Overview

This guide provides the instructions for building a Streamlit application using Snowpark for Python and <strong><span style="color: blue;">[Cybersyn data](https://app.cybersyn.com/data_catalog/)</span></strong> from the Snowflake Marketplace.

## What we will build

A Streamlit application that loads and visualizes daily <strong>stock performance</strong> and <strong>foreign exchange (FX) rate</strong> data loaded from <strong><span style="color: blue;">[Cybersyn](https://app.snowflake.com/marketplace/listing/GZTSZAS2KF7/cybersyn-financial-economic-essentials)</span></strong> on the Snowflake Marketplace using Snowpark for Python.

Put the gif here

### What is Snowspark?

The set of libraries and runtime in Snowflake that securely deploy and process non-SQL code, including Python, Java and Scala.

<strong>Familiar Client Side Libraries</strong> - Snowflake brings deeply integrated, Data-Frame style programming and OSS compatible APIs to the language data practitioners like to use. It also includes the Snowpark ML API for more efficient ML modelling (public preview) and ML operations (private preview).

<strong>Flexible Runtime Constructs</strong> - Snowpark provides flexible runtime constructs that allow users to bring in and run custom logic. Developers can seamlessly build data pipelines, ML models, and data applications with User-Defined Functions and Stored Procedures.

Learn more about <strong><span style="color: blue;">[Snowpark](https://snowflake.com/en/data-cloud/snowpark/)</span></strong>

<br>

<p align="center">
  <img src="https://github.com/AvinashhMishraa/real-time-stock-analysis/blob/main/Media/Snowpark%20Workflow.PNG">
</p>

<br>

### What is Streamlit?

Streamlit enables data scientists and Python developers to combine Streamlit's component-rich, open-source Python library with the scale, performance, and security of the Snowflake platform.


### What is Cybersyn?

<strong><span style="color: blue;">[Cybersyn](https://app.cybersyn.com/data_catalog/)</span></strong> is a data-as-a-service-company creating a real-time view of the world's economy with analytics-ready economic data on Snowflake Marketplace. Cybersyn builds derived data products from datasets that are difficult to procure, clean, or join. With Cybersyn, you can access external data directly in your Snowflake instance - no ETL requred.

### Prerequisites

1. A Snowflake account in AWS US Oregon

2. Access to the Financial & Economic Essentials dataset provided by Cybersyn.

   <div style="margin-left: 40px">In the Snowflake Marketplace, click on Get Data and follow the instructions to gain access. In particular, we will use data in schema CYBERSYN from tables STOCK_PRICE_TIMESERIES and FX_RATES_TIMESERIES.</div>

