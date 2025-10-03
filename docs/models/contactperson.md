# ContactPerson

ContactPerson

## Example Usage

```typescript
import { ContactPerson } from "@egain/egain-api-typescript/models";

let value: ContactPerson = {
  firstName: "Jocelyn",
  email: [],
};
```

## Fields

| Field                                | Type                                 | Required                             | Description                          |
| ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ |
| `firstName`                          | *string*                             | :heavy_check_mark:                   | First name of the customer           |
| `middleName`                         | *string*                             | :heavy_minus_sign:                   | Middle name of the customer          |
| `lastName`                           | *string*                             | :heavy_minus_sign:                   | Last name of the customer            |
| `email`                              | [models.Email](../models/email.md)[] | :heavy_check_mark:                   | Email details                        |
| `phone`                              | [models.Phone](../models/phone.md)[] | :heavy_minus_sign:                   | Phone details                        |