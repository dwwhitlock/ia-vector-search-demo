# ia-vector-search-demo
Demo of Databricks vector search &amp; integration with AI tools

Prerequisites: 
* Install this https://brew.sh/
* Mac or linux CLI
* Have an Databricks workspace that can provision AWS compute. Reference "traditional workspace" here https://docs.databricks.com/aws/en/admin/workspace/



```shell
brew install httrack
httrack https://fcsinnovationacademy.fultonschools.org/ \
  -O "~/websites/ia_website" \
  -%v --display -r2 -a
  
  
brew tap databricks/tap
brew install databricks
databricks auth login
cd ~/websites
databricks fs cp -r ia_website dbfs:/Volumes/personal_aws/default/innovation_academy
```