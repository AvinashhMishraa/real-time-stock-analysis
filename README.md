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
  <img src="Media/Snowpark Workflow.PNG">
</p>

<br>

### What is Streamlit?

Streamlit enables data scientists and Python developers to combine Streamlit's component-rich, open-source Python library with the scale, performance, and security of the Snowflake platform.


### What is Cybersyn?

<strong><span style="color: blue;">[Cybersyn](https://app.cybersyn.com/data_catalog/)</span></strong> is a data-as-a-service-company creating a real-time view of the world's economy with analytics-ready economic data on Snowflake Marketplace. Cybersyn builds derived data products from datasets that are difficult to procure, clean, or join. With Cybersyn, you can access external data directly in your Snowflake instance - no ETL requred.

### Prerequisites

1. A <strong><span style="color: blue;">[Snowflake](https://www.snowflake.com/en/)</span></strong> account in <strong>AWS US Oregon</strong>

2. Access to the <strong>Financial & Economic Essentials</strong> dataset provided by <strong>Cybersyn</strong>.

       
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In the <strong><span style="color: blue;">[ Snowflake Marketplace](https://app.snowflake.com/marketplace/listing/GZTSZAS2KF7/cybersyn-financial-economic-essentials)</span></strong>, click on <strong>Get Data</strong> and follow the instructions to gain access. <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In particular, we will use data in schema <strong>CYBERSYN</strong> from tables <strong><span style="background-color: yellow">STOCK_PRICE_TIMESERIES</span></strong> and <strong>FX_RATES_TIMESERIES</strong>.

<br>

We can have a look at the data description from the link above, but here is a sample view of <strong><span style="background-color: yellow">STOCK_PRICE_TIMESERIES</span></strong> (65.6 million rows) :

<p align="center">
  <img src="Media/Sample Data View - stock price.PNG">
</p>

<br>

And here is the sample view of <strong><span style="background-color: yellow">FX_RATES_TIMESERIES</span></strong> (1.0 million rows) :

<p align="center">
  <img src="Media/Sample Data View - FX Rates Timeseries.PNG">
</p>

<br>

# 2. Get Started

Follow these steps to start building Streamlit application in Snowsight.

<strong>Step 1.</strong> Click on <strong>Streamlit</strong> on the left navigation menu

<strong>Step 2.</strong> Click on <strong>+ Streamlit App</strong> on the top right

<strong>Step 3.</strong> Enter <strong>App name</strong>

<strong>Step 4.</strong> Select <strong>Warehouse</strong> (X-Small) and <strong>App location</strong> (Database and Schema) where you'd like to create the Streamlit applicaton

<strong>Step 5.</strong> Click on <strong>Create</strong>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;At this point, we will be provided code for an example Streamlit application

<strong>Step 6.</strong> Replace sample application code displayed in the code editor on the left by following instructions in the subsequent steps

<br>

### 3. Application Setup

Delete existing sample application code in the code editor on the left and add the following code snippet at the very top.


```python
# Import libraries in red
from snowflake.snowpark.context import get_active_session
from snowflake.snowpark.functions import sum, col, when, max, lag
from snowflake.snowpark import Window
from datetime import timedelta
import altair as alt
import streamlit as st
import pandas as pd

# Set page config in red
st.set_page_config(layout="wide")

# Get current session in red
session = get_active_session()
```

In the above code snippet, we're importing the required libraries, setting the application's page config to use full width of the browser window, and gaining access to the current session.

<br>

### 4. Load and Transform Data

Now add the following Python function that loads and caches data from the  
```diff
 + FINANCIAL__ECONOMIC_ESSENTIALS.CYBERSYN.STOCK_PRICE_TIMESERIES in green
```
and
```diff
+ FINANCIAL__ECONOMIC_ESSENTIALS.CYBERSYN.FX_RATES_TIMESERIES in green
```
tables.


<br>

```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```

<br>




<br>

<code style="color : name_color">texhhsjjst</code>
