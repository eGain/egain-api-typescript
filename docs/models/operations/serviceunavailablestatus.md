# ServiceUnavailableStatus

**Health Status**

The overall health status of the service. Possible values:
- **healthy**: Service is operating normally
- **degraded**: Service is functional but with performance issues
- **unhealthy**: Service is experiencing critical issues
- **maintenance**: Service is under planned maintenance


## Example Usage

```typescript
import { ServiceUnavailableStatus } from "@egain/egain-api-typescript/models/operations";

let value: ServiceUnavailableStatus = "healthy";
```

## Values

```typescript
"healthy" | "degraded" | "unhealthy" | "maintenance"
```