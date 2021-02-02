gcloud buildpack
----------------




## Test

```
pack build sample-gcloud-app \
  --path ./sample-gcloud-app \
  --buildpack ./buildpack \
  --builder gcr.io/buildpacks/builder:v1 \
  --run-image ghcr.io/jamesward/gcloud-buildpack-run

export GOOGLE_APPLICATION_CREDENTIALS=YOUR_TEST_CREDS_JSON

docker run --rm \
  -eCLOUDSDK_AUTH_CREDENTIAL_FILE_OVERRIDE=/certs/svc_account.json \
  -v$GOOGLE_APPLICATION_CREDENTIALS:/certs/svc_account.json \
  --entrypoint=projects \
  sample-gcloud-app
```
