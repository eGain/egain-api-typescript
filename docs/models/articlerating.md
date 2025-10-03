# ArticleRating

This schema contains general information about the article rating.

## Example Usage

```typescript
import { ArticleRating } from "@egain/egain-api-typescript/models";

let value: ArticleRating = {};
```

## Fields

| Field                                                                                                               | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                | *string*                                                                                                            | :heavy_minus_sign:                                                                                                  | The ID of the rating.                                                                                               |
| `articleId`                                                                                                         | *string*                                                                                                            | :heavy_minus_sign:                                                                                                  | The ID of the article.<br><br>An article ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `ratingValue`                                                                                                       | *number*                                                                                                            | :heavy_minus_sign:                                                                                                  | The score value of the rating. This must be a value between 0 and 100.                                              |
| `ratingComments`                                                                                                    | *string*                                                                                                            | :heavy_minus_sign:                                                                                                  | Comments about the rating.                                                                                          |
| `userId`                                                                                                            | *string*                                                                                                            | :heavy_minus_sign:                                                                                                  | The ID of the user that rated the article.                                                                          |
| `ratingTimestamp`                                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)                       | :heavy_minus_sign:                                                                                                  | The timestamp for when the article was rated.                                                                       |