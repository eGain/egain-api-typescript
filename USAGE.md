<!-- Start SDK Example Usage [usage] -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.postPortalIDRetrieve({
    q: "fair lending",
    portalID: "PROD-1000",
    dollarFilterUserProfileID: "PROD-3210",
    language: "en-US",
    dollarFilterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    dollarFilterTopicIds: [
      "PROD-2000",
    ],
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->