# AccessSource

Provides information about the method in which the Article is accessed and is used for self-service analytics. Refer to the eGain User Guide regarding "Article View Contexts".

| Name | Description 
| ---- | -----------
| article_view | View an Article directly using its ID.
| article_view_more_related_Article  | View related articles of an Article using its ID.
| article_view_basic_search | View an Article via a basic search.
| article_view_adv_search | View an Article via an advanced search.
| article_view_guided_help | View an Article via a Guided Help solution.
| article_view_browse_topic | View an Article via browsing a topic.
| article_view_browse_tree | View an Article via browsing a topic tree.
| article_view_popular_articles | View an Article using the Popular Items list in the Self-Service portal.
| article_view_useful_items | View Article using the Useful Items list in the Self-Service portal.
| article_view_widget | View an Article via a widget.
| article_view_announcement | View an Article from the announcement section in the Self-Service portal.
| article_view_bookmarked | View a bookmarked Article.
| article_view_subscription_notification | View an Article from a subscription notification.
| article_view_guided_help_additional_info | View an Article via additional information from a Guided Help search.
| view_articles_pending_compliance | View an Article via Read & Sign in the Self-Service portal.
| type_ahead_Suggestion | View an Article from a type-ahead Suggestion in the Self-Service portal.
| semantic_Suggestion | View an Article from a semantic Suggestion in the Self-Service portal.
| instant_answer | View an Article via an Instant Answers solution.
| instant_answer_reference | View an Article that is used as a reference for an Instant Answers solution.


## Example Usage

```typescript
import { AccessSource } from "@egain/egain-api-typescript/models/operations";

let value: AccessSource = "article_view";
```

## Values

```typescript
"article_view" | "article_view_more_related_Article" | "article_view_basic_search" | "article_view_adv_search" | "article_view_guided_help" | "article_view_browse_topic" | "article_view_browse_tree" | "article_view_popular_articles" | "article_view_useful_items" | "article_view_widget" | "article_view_announcement" | "article_view_bookmarked" | "article_view_subscription_notification" | "article_view_guided_help_additional_info" | "view_articles_pending_compliance" | "type_ahead_Suggestion" | "semantic_Suggestion" | "instant_answer" | "instant_answer_reference"
```