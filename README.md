# bq-query

A wrapper for the BigQuery command-line.

## Motivation

BigQuery queries may be executed from the [Cloud console](https://console.cloud.google.com/bigquery) or from the [command-line](https://cloud.google.com/bigquery/docs/reference/bq-cli-reference). My preferred method is the CLI as it allows me to run queries, save the results to file and then return to them later. The Cloud console feels slow and requires you to be engaged with your browser. If your machine sleeps while waiting for results, then you would need to re-run the query. It also doesn't save the results to file automatically.

## Prerequisites

- Confirm that you have a supported version of Python. The Google Cloud CLI requires Python 3 (3.5 to 3.8, 3.7 recommended) and Python 2 (2.7.9 or higher).
- Install the [gcloud CLI](https://cloud.google.com/sdk/docs/install).
- Initialize the glcoud CLI, login to your Google account and pick your cloud project.
```
./google-cloud-sdk/bin/gcloud init
```

## Usage

```sh
$ ./bq-query test/test.sql

+---------------+-------+
|     word      | count |
+---------------+-------+
| praising      |     8 |
| Praising      |     4 |
| raising       |     5 |
| dispraising   |     2 |
| dispraisingly |     1 |
| raisins       |     1 |
+---------------+-------+
```

**Save results to file:**

```sh
$ ./bq-query test/test.sql --output ./results.csv --format=csv
```

See help for usage instructions.
```sh
./bq-query --help
```

## License and Copyright

This software is released under the terms of the [MIT license](https://github.com/kevinfarrugia/bq-query/blob/main/LICENSE).
