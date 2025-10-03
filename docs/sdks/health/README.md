# Health
(*content.health*)

## Overview

### Available Operations

* [getHealth](#gethealth) - Check service health status

## getHealth

# Service Health Check

## Overview
This API provides comprehensive health status information for the Import Content service. It's designed for infrastructure monitoring, load balancer health checks, and operational monitoring to ensure service availability and performance.

## Health Check Features
- **Service Status**: Overall service health (healthy/unhealthy)
- **Version Information**: Current API version and build details

## Monitoring Use Cases
- **Load Balancers**: Automatic health checks for traffic routing
- **Alerting Systems**: Automated notifications for service issues

## Health Status Values
- **Healthy**: Service is operating normally
- **Unhealthy**: Service is experiencing critical issues
- **Maintenance**: Service is under planned maintenance

## Response Components
- **Status**: Current health state
- **Timestamp**: When health check was performed
- **Version**: API version information
- **Uptime**: Service uptime since last restart

## Monitoring Best Practices
- **Check Frequency**: Monitor every 1-2 minutes for production
- **Response Time**: Track health check response times

## Permissions
| Actor | Permission |
| ------- | --------|
| System |<ul><li>No authentication required for basic health checks.</li><li>This endpoint is designed for infrastructure monitoring.</li><li>Rate limiting applies to prevent abuse.</li></ul>|


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getHealth" method="get" path="/import/content/health" -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.content.health.getHealth();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { contentHealthGetHealth } from "@egain/egain-api-typescript/funcs/contentHealthGetHealth.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await contentHealthGetHealth(egain);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("contentHealthGetHealth failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.GetHealthResponse](../../models/operations/gethealthresponse.md)\>**

### Errors

| Error Type                     | Status Code                    | Content Type                   |
| ------------------------------ | ------------------------------ | ------------------------------ |
| errors.ServiceUnavailableError | 503                            | application/json               |
| errors.EgainDefaultError       | 4XX, 5XX                       | \*/\*                          |