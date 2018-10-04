# Snyk Codefresh Example
This example application has a sample application along with a Codefresh pipeline that can build, scan, and promote a Docker image. 

*Warning* These instructions are incomplete. Some variables in the pipeline need to be updated to match your environment. Update coming soon. 
## Instructions

### Pre-requisites 
- [Codefresh account](https://codefresh.io/) (free or paid)
- [Snyk account](https://snyk.io/) (free or paid)
- Dockerhub account (Optional)

### Add Repo to Codefresh
Signin to Codefresh and click "Add Repository" from the [repositories screen](https://g.codefresh.io/repositories). Paste in the url for this repo and click next. Then select "I have a Codefresh.yml" and put `./.codefresh/codefresh.yml` for the path. This will preview the Codefresh yaml, then follow the instructions to finish creating the pipeline.

### Add Environmental Variables 
You can type in the variables by hand, or just copy and paste the following:
```
PORT=8080
SNYK_ORG=aarlaud-snyk-demo
IMAGE_NAME=aarlaudsnyk/trainingapp
SNYK_TOKEN=addapikeyhere
```

Select "Import from Text" to import. 

We'll also add a token from Snyk. You can get this from your [Snyk account settings](https://app.snyk.io/account). Add this variable with `SNYK_TOKEN` as the key. Then check encrypt to store the token securely. 

### Add Dockerhub (optional)
Codefresh has a built-in private Docker registry. In this example we're building and pushing a public image so we'll use Docker hub. Follow the instructions in the [Docker Registry integration page](https://g.codefresh.io/account-conf/integration/registry).

You can skip this step by removing the promote to Dockerhub step. 

### Go run your pipelne. 