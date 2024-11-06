# BigLake: Qwik Start || [GSP1040](https://www.cloudskillsboost.google/focuses/37985?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

```
export PROJECT_ID=$(gcloud config get-value project)

bq mk --connection --location=US --project_id=$PROJECT_ID --connection_type=CLOUD_RESOURCE my-connection

SERVICE_ACCOUNT=$(bq show --format=json --connection $PROJECT_ID.US.my-connection | jq -r '.cloudResource.serviceAccountId')

gcloud projects add-iam-policy-binding $PROJECT_ID \
  --member=serviceAccount:$SERVICE_ACCOUNT \
  --role=roles/storage.objectViewer

bq mk demo_dataset

bq mkdef \
--autodetect \
--connection_id=$PROJECT_ID.US.my-connection \
--source_format=CSV \
"gs://$PROJECT_ID/invoice.csv" > /tmp/tabledef.json

bq mk --external_table_definition=/tmp/tabledef.json --project_id=$DEVSHELL_PROJECT_ID demo_dataset.biglake_table

bq mk --external_table_definition=/tmp/tabledef.json --project_id=$DEVSHELL_PROJECT_ID demo_dataset.external_table

bq show --schema --format=prettyjson  demo_dataset.external_table > /tmp/schema

bq update --external_table_definition=/tmp/tabledef.json --schema=/tmp/schema demo_dataset.external_table
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
