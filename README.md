# Rill Workshop Instructions

## Creating your git commits project

1. Install Rill:
   ```bash
   curl https://rill.sh | sh -s -- --nightly
   ```

2. **Add Data** → Select **Google Cloud Storage** → Skip credentials part (It's a public source)

   Location:
   ```
   gs://rilldata-public/db_repos/commits.json.gz
   ```

## Enable AI Features in Rill Developer

Add the following to `rill.yaml`:

```yaml
features: 
  - developerChat
  - generateCanvas
```

Note: These features are in active development and thus behind a feature flag.

## Use AI to generate the following

- Commits Metrics View
- Explore dashboard
- Canvas dashboard

## Using AI as a copilot, make changes to metrics view

- Remove the dimension hash - Not useful on dashboards
- Add a new dimension commit_uri that points to commits on GitHub
- Add a new measure for the number of committers as count distinct authors
- Get familiar with code files

## Quick Data Modeling

Add a new model to convert commit-based data into file-based changes: 
See [models/file_changes.sql](models/file_changes.sql)

### A more curated Metrics View for file-based changes 
See [metrics/file_changes_metrics.yaml](metrics/file_changes_metrics.yaml)

### Explore the data 

- What key insights can you find ? 

## Conversational AI

- Which project has been most active in the last year?
- How many commits were reverted in the last year?
- Who are the most active committers for all time?
- Show me a comparison of ClickHouse and DuckDB commits over time?

## Deploy the project and share with others 

## Connect using MCP server 
https://docs.rilldata.com/explore/mcp

## Security policies 
https://docs.rilldata.com/build/metrics-view/security



