# restSE2pp
bioinfo 2pp for restfulSE

To use pancan_SE() you must have a BigQuery project ID (which must be
established through the BigQuery app in Google Cloud Platform, implying that you
have provided a payment method -- all accounts receive $300 in credit, but some
payment method must be supplied.) See [The BigQuery Getting Started Docs][1] for
details. The project ID can be recoverd from the 'settings' section of the
'[IAM & admin][2]' page

[1]: https://cloud.google.com/bigquery/docs/quickstarts/quickstart-web-ui
[2]: https://console.cloud.google.com/iam-admin/iam

Set the environment variable `CGC_BILLING` to the project ID that you have
established, or use this project ID as a string for the billing parameter in
pancan_BQ.

After establishing the project ID, you can visit the following URL

https://console.cloud.google.com/bigquery?p=pancancer-atlas&page=project

and this event will prompt for authentication.  

At this point,
```
bq = BiocOncoTK::pancan_BQ()
bigrquery::dbListTables(bq)
```
should succeed, but it may provoke an authentication event.  Be sure that the
google identity you authenticate with matches the identity used to establish the
BigQuery project to which pancancer-atlas is linked.
