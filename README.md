This project aims to setup a Kong Enterprise dev environment with http-log and fluentbit consuming the logs from http-log



##Command to set-up http-log:

ADMIN_URL="http://localhost:8001"
TOKEN="admin123"

curl -i -X POST "${ADMIN_URL}/plugins" \
  -H "Kong-Admin-Token: ${TOKEN}" \
  --data "name=http-log" \
  --data "config.http_endpoint=http://fluentbit:2020" \
  --data "config.method=POST" \
  --data "config.timeout=10000" \
  --data "config.keepalive=60000"
