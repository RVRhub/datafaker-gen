## DataFaker Gen BigQuery Sink

The BigQuery Sink allows for the generation and sending of data to Google BigQuery.
This sink can generate and send documents either individually or in batches in one message. It depends on `batchSize` property specified in `output.yaml` configuration.

## How to run 

### Configure BigQuery Sink

All configuration is in `output.yaml` file.
```bash
sinks:
  bigquery:
    batchsize: 10
    project_id: _project_id_
    dataset: datafaker
    table: users
    service_account: path_to_service_account.json
    create_table_if_not_exists: true
    max_outstanding_elements_count: 100
    max_outstanding_request_bytes: 10000
    keep_alive_time_in_seconds: 60
    keep_alive_timeout_in_seconds: 60
```

### Run

```bash
 bin/datafaker_gen -f json -n 10000 -sink bigquery 
```

## TODO
 
 - [ ] Add support for more data types (date, timestamp, array, etc.)
 - [ ] Add support for more configuration options (create table, etc.)
