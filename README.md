# gitlabci-docker-git-gcloud
docker:git image with Google Cloud SDK and kubectl for Gitlab CI Runner

## Usage

This is the alpine based `docker:git` image, with the Google Cloud SDK and kubectl added.

It can be used as a foundation to automate _Google Cloud Container Engine_ deployments via gcloud and kubectl commands.

To get started, create a `Service account key` via Google Cloud's API Manager in the Credentials section in JSON format.

I'm storing the entire contents of the JSON file in a Gitlab Variable, which I then write out to a file.

Afterwards, authenticate to Google Cloud with:

    # gcloud auth activate-service-account --key-file=your-credentials-file.json

Then, retrieve the credentials to make them available to kubectl via:

    # gcloud container clusters get-credentials <your-cluster-id>

Afterwards, run whatever typical `kubectl apply -f` scripts, etc.

