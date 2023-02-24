# Prometheus Architcture

![](Pasted%20image%2020230129133414.png)

## Prometheus server
Prometheus server contains 3 components.
- Retrieval - which scapes the data or metrics from end points
- Then the retrived data is stored in local storage as custom time series database.
- The Stored data is ade available over HTTP server for promotheus webUI or Visulization tools like grafana.

Any one can query the prometheus data using promql, which is a readonly querying language.

### Retrieval
Prometheus scrapes/pulls the metrics from targets (Jobs/Exporters) over HTTP.
the apps or servers need not to send the data.
Jobs can be custom jobs.
Pre defined Exporters are available for most of the common targets, like windows , Linux machine exporters.

## Pushgateway
in case of shrt lived jobs, pull mechanism doesn't work to scrape the metrics.
in this case the jobs will push the etrics to intermediate pushgateway and prometheus  will pull the data fom gateway.

## Service discovery
Service discovery helps prometheus aware of the targets to be monitored dynamically.

## Data visualization and export
The scraped data made available to the users through Prometheus webUI
Grafana can be used to visualize the data.
By using the API client any third party tool can be integrated to visualize the data.

## Prometheus alerting
Prometheus server will push the alerts to the alert manager and alert manager will notify the users over email, text or pager, depending on the alert configuration.

