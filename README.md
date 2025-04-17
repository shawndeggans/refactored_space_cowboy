# Refactored Space Cowboy

## Databricks Tagging Strategies

A comprehensive guide to implementing effective tagging strategies in Databricks environments.

## Overview

The `tagging_strategies.ipynb` notebook provides practical implementations and examples for utilizing Databricks' three distinct tagging systems:

1. **Resource-level tagging**: For attributing compute costs to teams, projects, or users
2. **Unity Catalog securable object tagging**: For organizing, classifying, and governing data assets
3. **Serverless compute workload tagging**: For tracking usage of serverless resources

## Features

- **Python Implementations**: Ready-to-use Python functions for applying tags to various Databricks resources
- **Tag Management**: Methods for adding, updating, and removing tags across different resource types
- **Resource Optimization**: Best practices for using tags to manage compute costs and resource allocation
- **Data Governance**: Techniques for classifying and organizing data assets in Unity Catalog
- **API Integration**: Examples of interacting with Databricks REST APIs for tagging operations

## Prerequisites

- An active Databricks workspace
- Python 3.7+
- PySpark
- Access to Databricks REST APIs
- Required permissions for managing the resources you want to tag

## Getting Started

1. Clone this repository:
```bash
git clone https://github.com/shawndeggans/refactored_space_cowboy.git
```

2. Navigate to the project directory:
```bash
cd refactored_space_cowboy/budget_nb
```

3. Install the required dependencies:
```bash
pip install python-dotenv requests
```

4. Create a `.env` file with your Databricks credentials:
```
TOKEN=your_databricks_token
DATABRICKS_INSTANCE=your_databricks_instance
CLUSTER_ID=your_cluster_id_for_testing
WAREHOUSE_ID=your_warehouse_id_for_testing
```

5. Import the notebook into your Databricks workspace.

## Resource Tagging Examples

The notebook includes examples for tagging various Databricks resources:

- **Clusters**: Tag all-purpose and job clusters with custom attributes
- **SQL Warehouses**: Apply tags to SQL warehouses for cost tracking
- **Unity Catalog Objects**: Tag catalogs, schemas, tables, and columns
- **Tag Management**: Add, update, and remove tags programmatically

## Best Practices

- Use consistent tagging conventions across your organization
- Apply tags at multiple levels (workspace, cluster, table, etc.) for comprehensive tracking
- Leverage tags for budget forecasting and cost optimization
- Implement tags as part of your data governance strategy
- Automate tag application through CI/CD pipelines

## Contact

For questions or collaboration opportunities, please contact Shawn Deggans:

- GitHub: [@shawndeggans](https://github.com/shawndeggans)