# Restyled QA

Harness for full-integration testing of Restyled.io.

## Pre-requisites

Create a `.env` file with

1. `GITHUB_APP_KEY_BASE64` - RSA key for our Development GitHub App

   ```console
   base64 < path/to/rsa | tr -d '\n'
   ```

1. `NGROK_AUTHTOKEN` - token for our ngrok account

## Usage

1. Build release-candidate images from sibling directories

   ```console
   (cd ../restyler && make image.build IMAGE_TAG=:rc)
   (cd ../restyled.io && make image.build LOCAL_IMAGE=restyled/restyled.io:rc)
   ```

   **NOTE**: The currently-released `:latest` tags of individual Restylers are
   always pulled and used. Therefore, do not use this Harness to test local
   changes within any given Restyler.

1. Start a complete local instance of Restyled.io

   ```console
   docker-compose up -d
   ```

1. Run the QA test(s)

   ```console
   # TODO
   ```

1. Stop your local instance

   ```console
   docker-compose down
   ```
