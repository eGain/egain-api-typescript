# SuggestionL10NString

The status of the Suggestion.
<li>1 : suggested.</li>
<li>2 : pending</li>
<li>3 : declined</li>
<li>4 : approved</li>

## Example Usage

```typescript
import { SuggestionL10NString } from "@egain/egain-api-typescript/models";

let value: SuggestionL10NString = {};
```

## Fields

| Field                                  | Type                                   | Required                               | Description                            |
| -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| `value`                                | *string*                               | :heavy_minus_sign:                     | A string that indicates the value.     |
| `displayValue`                         | *string*                               | :heavy_minus_sign:                     | Localized string of the value element. |