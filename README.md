# dbt-profiles-jsonschema

A JSON Schema for validating `profiles.yml` files in dbt projects.

There is a main `dbt_profiles_schema.json` file that defines the schema for the `profiles.yml` file. This schema is based on the [dbt profiles.yml documentation](https://docs.getdbt.com/docs/core/connect-data-platform/profiles.yml).

In the `types` folder, there are additional JSON Schema files that define the schema for selected types defined in the `outputs.<target_name>.type` field. These are referenced in the main schema file. Example:

```json
{
    "if": {
        "properties": {
            "type": {
                "const": "snowflake"
            }
        }
    },
    "then": {
        "$ref": "snowflake_schema.json"
    }
}
```

## Inspiration

Thanks to [dbt-labs and their own repository](https://github.com/dbt-labs/dbt-jsonschema) for providing inspiration for this project. The repository contains other schemas for other dbt YAML files.

[Fivetran also had an old repository](https://github.com/fivetran/dbt_yaml_schemas/blob/main/schemas/profiles.json) with a JSON Schema for `profiles.yml` files, but it is outdated and not maintained.

## Usage

We recommend following the [guide in the dbt-labs repository](https://github.com/dbt-labs/dbt-jsonschema) for linting various dbt YAML files.

### Example

In VSCode, with the [VSCode-YAML extension](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) installed:

```json
{
    "yaml.schemas": {
        "https://raw.githubusercontent.com/orchestra-hq/dbt-profiles-jsonschema/main/dbt_profiles_schema.json": [
            "profiles.yml",
        ],
    },
}
```

## Contribution

PRs or GitHub issues are very welcome on this project, especially new connection types that this schema could support. If adding a new connection type, please follow the existing conventions. It will make approving and merging the PR quicker!

## Supported connection types

| Connection     | Supported | Schema |
|----------------|-----------|--------|
| Athena         | ✅        | [athena.json](types/athena.json) |
| BigQuery       | ❌        |        |
| Clickhouse     | ❌        |        |
| Databend       | ❌        |        |
| Databricks     | ❌        |        |
| Decodable      | ❌        |        |
| Doris          | ❌        |        |
| Dremio         | ❌        |        |
| Duckdb         | ❌        |        |
| Exasol         | ❌        |        |
| Extrica        | ❌        |        |
| Fabric         | ❌        |        |
| Firebolt       | ❌        |        |
| AWS Glue       | ❌        |        |
| Greenplum      | ❌        |        |
| Hive           | ❌        |        |
| ibmdb2         | ❌        |        |
| Impala         | ❌        |        |
| Infer          | ❌        |        |
| iomete         | ❌        |        |
| layer_bigquery | ❌        |        |
| Materialize    | ❌        |        |
| Mindsdb        | ❌        |        |
| Mysql          | ❌        |        |
| Oracle         | ❌        |        |
| Postgres       | ❌        |        |
| Redshift       | ❌        |        |
| Risingwave     | ❌        |        |
| Rockset        | ❌        |        |
| Singlestore    | ❌        |        |
| Snowflake      | ✅        | [snowflake.json](types/snowflake.json) |
| Spark          | ❌        |        |
| Sqlite         | ❌        |        |
| Sqlserver      | ❌        |        |
| Starrocks      | ❌        |        |
| Synapse        | ❌        |        |
| Teradata       | ❌        |        |
| Tidb           | ❌        |        |
| Trino          | ❌        |        |
| Upsolver       | ❌        |        |
| Vertica        | ❌        |        |
| Yellowbrick    | ❌        |        |
