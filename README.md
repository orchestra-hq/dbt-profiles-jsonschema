# dbt-profiles-jsonschema

A [JSONSchema](https://json-schema.org/) project for validating `profiles.yml` files in dbt projects. The schema is based on the [dbt profiles.yml documentation](https://docs.getdbt.com/docs/core/connect-data-platform/profiles.yml). Specific properties for different connection types are included in this schema - see [Supported connection types](#supported-connection-types) for a list of supported connection types.

## Inspiration

Thanks to [dbt-labs and their own repository](https://github.com/dbt-labs/dbt-jsonschema) for providing inspiration for this project. The repository contains other schemas for other dbt YAML files, which we would recommend. [Fivetran also had an old repository](https://github.com/fivetran/dbt_yaml_schemas/blob/main/schemas/profiles.json) with a schema for `profiles.yml` files, but it is outdated and not maintained.

## Usage

We recommend following the [guide in the dbt-labs repository](https://github.com/dbt-labs/dbt-jsonschema) for linting various dbt YAML files. In VSCode, with the [VSCode-YAML extension](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) installed:

```json
{
    "yaml.schemas": {
        "https://raw.githubusercontent.com/orchestra-hq/dbt-profiles-jsonschema/main/dbt_profiles_schema.json": [
            "profiles.yml",
        ],
    },
}
```

If running the schema check programmatically, you can use the [check-jsonschema](https://pypi.org/project/check-jsonschema/) PyPi package:

```bash
pip install check-jsonschema
check-jsonschema --schemafile dbt_profiles_schema.json test_profiles.yml
```

## Contribution

PRs or GitHub issues are very welcome on this project, especially new connection types that this schema could support. If adding a new connection type, please follow the existing conventions. It will make approving and merging the PR quicker! All PRs are tested in GitHub Actions CI to make sure the example `profiles.yml` file passes the schema as expected.

## Supported connection types

| Connection     | Supported |
|----------------|-----------|
| Athena         | ✅        |
| BigQuery       | ❌        |
| Clickhouse     | ❌        |
| Databend       | ❌        |
| Databricks     | ❌        |
| Decodable      | ❌        |
| Doris          | ❌        |
| Dremio         | ❌        |
| Duckdb         | ❌        |
| Exasol         | ❌        |
| Extrica        | ❌        |
| Fabric         | ❌        |
| Firebolt       | ❌        |
| AWS Glue       | ❌        |
| Greenplum      | ❌        |
| Hive           | ❌        |
| ibmdb2         | ❌        |
| Impala         | ❌        |
| Infer          | ❌        |
| iomete         | ❌        |
| layer_bigquery | ❌        |
| Materialize    | ❌        |
| Mindsdb        | ❌        |
| Mysql          | ❌        |
| Oracle         | ❌        |
| Postgres       | ❌        |
| Redshift       | ❌        |
| Risingwave     | ❌        |
| Rockset        | ❌        |
| Singlestore    | ❌        |
| Snowflake      | ✅        |
| Spark          | ❌        |
| Sqlite         | ❌        |
| Sqlserver      | ❌        |
| Starrocks      | ❌        |
| Synapse        | ❌        |
| Teradata       | ❌        |
| Tidb           | ❌        |
| Trino          | ❌        |
| Upsolver       | ❌        |
| Vertica        | ❌        |
| Yellowbrick    | ❌        |
