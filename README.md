# Packer: By Example

This Repository contains a number of examples for using Packer, with different OS and CloudPlatforms
<https://aws.amazon.com/blogs/compute/query-for-the-latest-amazon-linux-ami-ids-using-aws-systems-manager-parameter-store/>

## AWS amis

## AWS Set-up

You will need to set-up and configured your AWS:

```cli
aws configure
```

When you run packer its is assumed that the following Environment variables are set:

```cli
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_SESSION_TOKEN
```

You can run

```bash
./build.sh -packfile ./packfiles/redhat/base-aws.json -environment
```

## GCP images

There is an example Debian image to run with GCP.

## GCP setup

If this is a new use of GCP you will have to run thru a bit of initial set-up.
When you run:

```bash
./build.sh -packfile ./packfiles/debian/base-gcp.json -environment
```

You will get errors like:

```bash
* googleapi: Error 403: Access Not Configured.
Compute Engine API has not been used in project 770172716123 before or it is disabled.
Enable it by visiting
 https://console.developers.google.com/apis/api/compute.googleapis.com/overview?project=770172716123 then retry.
If you enabled this API recently, wait a few minutes for the action to propagate to our systems and retry, accessNotConfigured

## Solution 1 Enable via https://console.developers.google.com/apis/api/compute.googleapis.com/overview?project=770172716123

## Solution 2 Via cli
From: https://cloud.google.com/endpoints/docs/openapi/enable-api

gcloud projects list

gcloud config set project [YOUR_PROJECT_ID]
gcloud config set project focused-elysium-224508

gcloud services list --available
gcloud services enable [SERVICE_NAME]
gcloud services enable Compute Engine API
```

## Azure Images
