# StringAttributeValue

An attribute can have an external value such as a readable label, and an internal value such as a unique ID. This schema provides both the internal and external values for one attribute.

## Example Usage

```typescript
import { StringAttributeValue } from "@egain/egain-api-typescript/models";

let value: StringAttributeValue = {};
```

## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `internalValue`                                | *string*                                       | :heavy_minus_sign:                             | The internal value of the attribute.           |
| `externalValue`                                | *string*                                       | :heavy_minus_sign:                             | The external or public value of the attribute. |