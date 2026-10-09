# ThingsPanel notification plugin: Alibaba Cloud SMS

Alibaba Cloud Dysmsapi template SMS. The optional MNS worker does not make this release receipt-capable; delivery_receipts and receipt_expected remain false until the trusted Core receipt path is verified.

This is an independent Go module for the frozen ThingsPanel notification plugin HTTP v1 contract. It includes the provider adapter, executable, tests, and a source snapshot of the portable SDK so it builds without Encore/Core imports or external Go dependencies. SDK source is maintained at [thingspanel-notification-plugin-sdk](https://github.com/ThingsPanel/thingspanel-notification-plugin-sdk); compare snapshots when upgrading.

## Build and test

```sh
GOPROXY=off GOSUMDB=off go test ./...
GOPROXY=off GOSUMDB=off go vet ./...
GOPROXY=off GOSUMDB=off go build ./cmd/plugin
```

Tests use local fixtures only. Running the executable does not authorize or perform a real provider send. Do not put credentials in source control or logs. `accepted` means provider submission acceptance, not delivery; uncertain outcomes are not automatically retried.

The module path is `github.com/ThingsPanel/thingspanel-notification-aliyun-sms`. This project is licensed under Apache-2.0.
