# Casebase

## Example Usage

```typescript
import { Casebase } from "@egain/egain-api-typescript/models";

let value: Casebase = {
  casebaseId: "409601000000001",
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `casebaseId`                                                         | *string*                                                             | :heavy_minus_sign:                                                   | The numerical ID of the Casebase.                                    | 409601000000001                                                      |
| `name`                                                               | *string*                                                             | :heavy_minus_sign:                                                   | name of the Casebase Release.                                        |                                                                      |
| `id`                                                                 | *string*                                                             | :heavy_minus_sign:                                                   | The numerical ID of the Casebase Release.                            |                                                                      |
| `status`                                                             | [models.CasebaseStatus](../models/casebasestatus.md)                 | :heavy_minus_sign:                                                   | status of the Casebase                                               |                                                                      |
| `profiles`                                                           | [models.ProfileResult](../models/profileresult.md)[]                 | :heavy_minus_sign:                                                   | All Guided Help Profiles associated with Casebase release            |                                                                      |
| `searchSettings`                                                     | [models.CasebaseSearchSettings](../models/casebasesearchsettings.md) | :heavy_minus_sign:                                                   | N/A                                                                  |                                                                      |
| `languages`                                                          | [models.KbLanguages](../models/kblanguages.md)                       | :heavy_minus_sign:                                                   | KB languages                                                         |                                                                      |
| `link`                                                               | [models.Link](../models/link.md)                                     | :heavy_minus_sign:                                                   | Defines the relationship between this resource and another object.   |                                                                      |