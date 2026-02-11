<!-- Start SDK Example Usage [usage] -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "What is a loan?",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-1030",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
      eventId: "6154589f-b43f-4471-b2c7-92c6c888a664",
      clientSessionId: "6154589f-b43f-4471-b2c7-92c6c888a643",
      sessionId: "6154589f-b43f-4471-b2c7-92c6c888a689",
    },
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->