# Deconz Exporter

Forked from [TobsCore/deconz-exporter](https://github.com/TobsCore/deconz-exporter) and modified to also support smart plugs with power measurement.

## Create Docker Image

Run the following commands:

```bash
# Build docker image
docker build .

# Run image (for testing)
docker run --expose 8081 -p 8081:8081 -e DECONZ_PORT=<deconz-rest-port> -e DECONZ_APP_PORT=8081 -e DECONZ_HOST=<deconz-rest-host> -e DECONZ_TOKEN=<deconz-rest-token> <image-id>

# Rename image
docker image tag <image-id> gyjch/deconz_exporter:latest

# Export image for installation on target
docker save -o build/deconz-exporter gyjch/deconz_exporter:latest

# Load image on target system
docker load -i <path to image tar file>
```
