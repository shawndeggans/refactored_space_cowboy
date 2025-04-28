# Databricks Budget Management System - User Guide

## Overview

This guide explains how to use the Databricks Budget Management System, a set of three notebooks that help you create, manage, and monitor budgets for your data analytics workloads.

## Prerequisites

1. Access to a Databricks workspace
2. Account admin permissions to create budget policies
3. The following environment variables set in a `.env` file or directly in your environment:
   - `ACCOUNT_HOST`: Databricks account URL
   - `ACCOUNT_ID`: Your Databricks account ID
   - `CLIENT_ID`: OAuth client ID
   - `CLIENT_SECRET`: OAuth client secret
   - `TOKEN`: Personal access token for workspace-level operations
   - `DATABRICKS_INSTANCE`: Your Databricks workspace URL

## The Three Notebooks

### 1. Budget_Setup_and_Management.ipynb

Create and manage budget policies with custom tags.

### 2. Budget_Cluster_Policy_Setup.ipynb

Link budget policies to cluster policies and synchronize tags.

### 3. Budget_Monitoring.ipynb

Monitor and analyze usage across your budget policies.

## Getting Started

### Step 1: Set Up Budget Policies

1. Open `Budget_Setup_and_Management.ipynb`
2. Enter a budget name (e.g., "Fraud Investigation Q2")
3. Add relevant tags:
   - Tag Key 1: `project` | Tag Value 1: `fraud-detection`
   - Tag Key 2: `department` | Tag Value 2: `investigations`
   - Tag Key 3: `quarter` | Tag Value 3: `Q2-2025`
4. Select "Create Budget" from the Action dropdown
5. Click "Execute Action"

### Step 2: Link Budget Policy to Cluster Policy

1. Open `Budget_Cluster_Policy_Setup.ipynb`
2. Under "Budget Policy Selection", choose your newly created budget policy
3. View the associated tags that will be applied
4. Under "Cluster Policy Management":
   - Enter a policy name (e.g., "Fraud Investigation Compute Policy")
   - Select a template type (Data Science, Data Engineering, or Analytics)
   - Set maximum clusters per user
   - Add an optional description
5. Click "Create Cluster Policy with Budget Tags"

### Step 3: Monitor Budget Usage

1. Open `Budget_Monitoring.ipynb`
2. Select your budget policy from the dropdown
3. Configure the analysis:
   - Select a tag key/value pair for filtering (optional)
   - Set the number of days to analyze
   - Choose the analysis type:
     - Overall Spending Analysis
     - Tag-Based Analysis
     - Cost Estimation
4. Click "Run Analysis" to generate visualizations and data tables

## Common Tasks

### Creating a New Budget for a Research Project

1. In `Budget_Setup_and_Management.ipynb`:
   - Enter budget name: "Financial Fraud Research 2025"
   - Add tags: `case_number: FR-2025-103`, `region: southwest`, `type: financial_fraud`
   - Create the budget

2. In `Budget_Cluster_Policy_Setup.ipynb`:
   - Select your newly created budget
   - Create a cluster policy using the "Data Science" template
   - Set a maximum of 5 clusters per user

3. Inform your analysts to select this cluster policy when creating clusters

### Managing Existing Cluster Policies

1. Open `Budget_Cluster_Policy_Setup.ipynb`
2. Click "Refresh Policies" to see all existing cluster policies
3. To update an existing policy with budget tags:
   - Select the cluster policy from the dropdown
   - Select a budget policy to use its tags
   - Click "Update with Budget Tags"

### Retiring a Budget

1. In `Budget_Setup_and_Management.ipynb`:
   - List all budgets to find the ID of the budget to retire
   - Enter the policy ID in the "Policy ID to Retire" field
   - Select "Retire Budget" from the Action dropdown
   - Click "Execute Action"

2. If needed, also delete the associated cluster policy in `Budget_Cluster_Policy_Setup.ipynb`

## Important Notes

1. Budget policy tags automatically propagate to clusters created with the linked cluster policy
2. Tag names can only contain letters, spaces, numbers, or the characters `+`, `-`, `=`, `.`, `_`, `:`, `/`, `@`
3. Changes to budget policies are not retroactive - they only apply to new resources
4. Analysis in the monitoring notebook requires access to system tables

## Troubleshooting

- **Authentication failures**: Verify your environment variables are set correctly
- **"No policies found"**: Ensure you have account admin permissions
- **Analysis errors**: Confirm access to `system.billing.usage` and other system tables
- **Tag sync issues**: Check for character restrictions in tag keys/values

For additional assistance, contact your Databricks administrator.