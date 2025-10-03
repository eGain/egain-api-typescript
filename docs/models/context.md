# Context

Additional contextual metadata that enriches the query, providing the LLM with relevant details for tailoring the response.

## Example Usage

```typescript
import { Context } from "@egain/egain-api-typescript/models";

let value: Context = {};
```

## Fields

| Field                                                                                                                 | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `userContext`                                                                                                         | *string*                                                                                                              | :heavy_minus_sign:                                                                                                    | Information about the end user (e.g., preferences, profile data, or behavioral signals).                              |
| `pageContext`                                                                                                         | *string*                                                                                                              | :heavy_minus_sign:                                                                                                    | Details about the UI or page where the query was initiated (e.g., page URL, section, or component).                   |
| `companyContext`                                                                                                      | *string*                                                                                                              | :heavy_minus_sign:                                                                                                    | Information about the organization associated with the user, used for tailoring responses in enterprise environments. |