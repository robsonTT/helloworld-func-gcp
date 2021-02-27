<img src="https://avatars2.githubusercontent.com/u/2810941?v=3&s=96" alt="Google Cloud Platform logo" title="Google Cloud Platform" align="right" height="96" width="96"/>

# Basic Example Google Cloud Functions - Hello World sample


![image](https://user-images.githubusercontent.com/54007079/109370073-90c4e500-787d-11eb-82f7-0f98e6ad8b0e.png)


![image](https://user-images.githubusercontent.com/54007079/109369316-af75ac80-787a-11eb-97e2-a8c3e36af5d6.png)


See:

* [Cloud Functions Hello World tutorial][tutorial]
* [Cloud Functions Hello World sample source code][code]

[tutorial]: https://cloud.google.com/functions/docs/quickstart
[code]: index.js

## Deploy and run the sample


- You can use some commands to make it easier to put on air, these commands will for example let you choose which geographic region your function will be in
![image](https://user-images.githubusercontent.com/54007079/109369601-b355fe80-787b-11eb-8e5e-dbc5ac78f846.png)


See the [Cloud Functions Hello World tutorial][tutorial].



**Note:** in order for the tests to run properly, you'll have to deploy some of the sample functions:

```
gcloud functions deploy helloHttp --runtime [YOUR_RUNTIME] --trigger-http
gcloud functions deploy helloPubSub --trigger-topic $FUNCTIONS_TOPIC --runtime [YOUR_RUNTIME]
gcloud functions deploy helloGCS --runtime [YOUR_RUNTIME] --trigger-resource $FUNCTIONS_DELETABLE_BUCKET --trigger-event providers/cloud.storage/eventTypes/object.change
```

* Replace `[YOUR_RUNTIME]` with the name of the runtime you are using. For a
complete list, see the [gcloud reference](https://cloud.google.com/sdk/gcloud/reference/functions/deploy#--runtime).

## Run the tests

1. Read and follow the [prerequisites](../../../../#prerequisites).


1. Install dependencies:

        npm install

1. Set the following environment variables:

        export GCF_REGION=us-central1
        export FUNCTIONS_TOPIC=[YOUR_PUBSUB_TOPIC]
        export FUNCTIONS_DELETABLE_BUCKET=[YOUR_CLOUD_STORAGE_BUCKET]  # will be deleted by tests!

1. Run the tests:

        npm test



