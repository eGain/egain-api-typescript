# StartEscalationRequest

## Example Usage

```typescript
import { StartEscalationRequest } from "@egain/egain-api-typescript/models";

let value: StartEscalationRequest = {
  subject: "<value>",
  body: "<value>",
  channel: "email",
  url: "https://straight-solvency.info/",
};
```

## Fields

| Field                                                                                      | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `customer`                                                                                 | [models.Customer](../models/customer.md)                                                   | :heavy_minus_sign:                                                                         | The contact point details of the customer who is starting the escalation.                  |
| `subject`                                                                                  | *string*                                                                                   | :heavy_check_mark:                                                                         | The subject of the email message.<br/>                                                     |
| `body`                                                                                     | *string*                                                                                   | :heavy_check_mark:                                                                         | The body of the email message.<br/>                                                        |
| `channel`                                                                                  | [models.ChannelEnum](../models/channelenum.md)                                             | :heavy_check_mark:                                                                         | The type of escalation<br/>                                                                |
| `url`                                                                                      | *string*                                                                                   | :heavy_check_mark:                                                                         | The url of the page that the customer was viewing at the time when the ecalation started.<br/> |
| `captcha`                                                                                  | [models.Captcha](../models/captcha.md)                                                     | :heavy_minus_sign:                                                                         | Only required when captcha is enabled for portal.<br/>                                     |