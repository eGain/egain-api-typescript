# SftpConfig

## Example Usage

```typescript
import { SftpConfig } from "@egain/egain-api-typescript/models";

let value: SftpConfig = {
  username: "rtka-user",
  password: "xyz1234",
  host: "sftp.yourcompany.com",
};
```

## Fields

| Field                           | Type                            | Required                        | Description                     | Example                         |
| ------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| `username`                      | *string*                        | :heavy_check_mark:              | N/A                             | rtka-user                       |
| `password`                      | *string*                        | :heavy_minus_sign:              | N/A                             | xyz1234                         |
| `host`                          | *string*                        | :heavy_check_mark:              | The hostname of the SFTP server | sftp.yourcompany.com            |
| `port`                          | *number*                        | :heavy_minus_sign:              | The server port number          |                                 |