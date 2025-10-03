<!-- Start SDK Example Usage [usage] -->
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  security: {
    oAuthUser: process.env["EGAIN_O_AUTH_USER"] ?? "",
  },
});

async function run() {
  const result = await egain.content.import.createImport({
    dataSource: {
      type: "AWS S3 bucket",
      path: "s3://mybucket/myfolder/",
      region: "us-east-1",
      credentials: {},
    },
    operation: "import",
    scheduleTime: {
      date: new Date("2024-03-01T10:00:00.000Z"),
    },
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->