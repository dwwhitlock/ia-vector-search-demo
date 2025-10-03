# ia-vector-search-demo
Demo of Databricks vector search & integration with AI tools for the [Innovation Academy](https://fcsinnovationacademy.fultonschools.org/)
IT Day on 10-3-2025

Prerequisites: 
* Install this https://brew.sh/
* Mac or linux CLI
* Have an Databricks workspace that can provision AWS compute. Reference "traditional workspace" here https://docs.databricks.com/aws/en/admin/workspace/
* Provisioned a catalog and schema (aka database), and volume - replace the env vars below with your values


```shell
brew install httrack
httrack https://fcsinnovationacademy.fultonschools.org/ \
  -O "~/websites/ia_website" \
  -%v --display -r2 -a
  
  
brew tap databricks/tap
brew install databricks
databricks auth login
cd ~/websites

export CATALOG_NAME=personal_aws
export SCHEMA=default
export VOLUME_NAME=innovation_academy
databricks fs cp -r ia_website dbfs:/Volumes/$CATALOG_NAME/$SCHEMA/$VOLUME_NAME
```

Once the docs have been uploaded, run the notebook on classic compute (NOT SERVERLESS) running 14.3-LTS. 
Click the link to view the vector search endpoint, then to use it with AI models, click "View in playground"
