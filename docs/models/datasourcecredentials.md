# DataSourceCredentials

## Example Usage

```typescript
import { DataSourceCredentials } from "@egain/egain-api-typescript/models";

let value: DataSourceCredentials = {};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `accessKey`                                                              | *string*                                                                 | :heavy_minus_sign:                                                       | Access key for S3 credentials datasource. Provide along with Secret Key. |
| `secretKey`                                                              | *string*                                                                 | :heavy_minus_sign:                                                       | Secret key for S3 credentials datasource. Provide along with Access Key. |
| `username`                                                               | *string*                                                                 | :heavy_minus_sign:                                                       | Username for SFTP credentials datasource. Provide along with Password.   |
| `password`                                                               | *string*                                                                 | :heavy_minus_sign:                                                       | Password for SFTP credentials datasource. Provide along with Username.   |