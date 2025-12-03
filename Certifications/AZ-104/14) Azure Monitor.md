**Azure Monitor** comprehensive solution for collecting, analying, and acting on telemetry from your cloud and on-premises environments
- Create Visual Dashboards
- Smart Alerts
- Automated Actions
- Log Monitoring

To obtain observability you need to use Metrics, Logs, and Traces
- you have to use them together, using them in isolate does not gain you observability
    - Metrics: A number that is measured over a period of time
    - Logs: A text file where each line contains event data about what happened at a certain time
    - Traces: A history of requests that travels through multiple Apps/Services so we can pinpoint performance or failure

Azure Monitor collects two fundamental types of data from sources: Logs and Metrics

**Azure Monitor Logs**: collects and organizes log and performance data from monitored resources
- Data logs are consolidated from different sources into workspaces
    - platform logs from Azure services
    - Log and performance data from virtual machines agents
    - usage and performance data from applications can be consolidated
    - In a workspace, so they can be analyzed together using a sophisticated query language capable of analyzing millions of records
- Work with log queries and their results interactively using Log Analytics

Azure Monitor Metrics collects numeric data from monitored resources into a time-series database
- Metrics are numerical values collected at regular intervals and describe some aspect of a system at a particular time
- Lightweight and capable of supporting near real-time scenarios, useful for alerting and fast detection of issues
- You can analyze them interactively with Metrics Explorer
Log Analytics is a tool in the Azure portal used to edit and run log queries with data in Azure Monitor Logs
- Log Analytics uses a query language called KQL
Log Analytics workspace is a unique environment for Azure Monitor log data
- Each workspace has its own data repository and configuration, data sources and solutions are configured to store their data in a workspace

Azure Monitor Logs is based on Azure Data Explorer, and log queries are written using the same Kusto Query Language (KQL)

KQL can be used in: Log Analytics, Log alert rules, Workbooks, Azure Dashboards, Logic Apps, PowerShell, Azure Monitor Logs API

Kusto is based on relational database management systems and supports entities such as databases, tables, and columns
- Some Query operators include
    - Calculated columns, searching, and filtering on rows, group by-aggregates, join functions
- Kusto queries execute in the context of some Kusto database that is attached to a Kusto cluster
- Kusto is generally composed of the following entites: Clusters, Databases, Tables, Columns, Functions
    - Clusters are entities that hold databases
    - Databases are named entities that hold tables and stored functions
    - Stored functions are named entities that allow