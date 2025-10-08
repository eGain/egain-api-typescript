# @egain/egain-api-typescript

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *@egain/egain-api-typescript* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=@egain/egain-api-typescript&utm_campaign=typescript"><img src="https://www.speakeasy.com/assets/badges/built-by-speakeasy.svg" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />


<!-- Start Summary [summary] -->
## Summary

Knowledge Portal Manager APIs: ### License
  The following licenses are required to use the Knowledge Access APIs:
  * If the user is an agent, then the *Knowledge + AI* license is required.
  * If the user is a customer, the *Self-Service* and *Advanced Self-Service* licenses must be available.

### Tiers

| Tier	|Tier Name|	Named Users |	Description
| ---------- | ---------- | ---------- | ----------------------------
| Tier 1 |  Starter |	Up to 10|	Designed for small-scale implementations or pilot environments
| Tier 2 |	Growth	| Up to 1000|	Suitable for mid-scale deployments requiring moderate scalability
| Tier 3 |	Enterprise	| Greater than 1000|	Supports large-scale environments with extended configuration options

### API Resource Limits
The following Resources have predefined limits for specific access attributes for Starter, Growth and Enterprise use.

| Resource | Limits | Starter | Growth | Enterprise
| ---------------- | ---------------------------- | ---------- | ---------- | ----------
| Article Reference |Number of attachments used in any article | 25 | 50 |50
|  |Number of custom attributes in an article | 10 | 25| 50 
|  |Number of publish views used in an article version | 20 | 20 | 20
| Topic Reference |User-defined topics in a department| 1000| 5000 | 50000
|  |Depth of topics  | 5 | 20 | 20
|  |Topics at any level | 500 | 2500 | 2500
|  |Number of custom attributes in a topic | 10 | 10 | 10
| Portal Reference | Tag categories in a portal | 15 | 15 | 15
|  |Topics to be included in a portal | 100 | 500 | 5000 
|  |Number of articles to display in announcements | 10 | 25 | 25
|  |Usage links and link groups setup for a portal | 5 | 10 | 25
    
      


For more information about the API: [Full SDK Documentation](https://github.com/eGain/egain-api-typescript)
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [@egain/egain-api-typescript](#egainegain-api-typescript)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [File uploads](#file-uploads)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add @egain/egain-api-typescript
```

### PNPM

```bash
pnpm add @egain/egain-api-typescript
```

### Bun

```bash
bun add @egain/egain-api-typescript
```

### Yarn

```bash
yarn add @egain/egain-api-typescript
```

> [!NOTE]
> This package is published with CommonJS and ES Modules (ESM) support.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name          | Type | Scheme      | Environment Variable |
| ------------- | ---- | ----------- | -------------------- |
| `accessToken` | http | HTTP Bearer | `EGAIN_ACCESS_TOKEN` |

To authenticate with the API the `accessToken` parameter must be set when initializing the SDK client instance. For example:
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

#### [aiservices.answers](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/answers/README.md)

* [getBestAnswer](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/answers/README.md#getbestanswer) - Get the best answer for a user query

#### [aiservices.retrieve](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/retrieve/README.md)

* [retrieveChunks](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/retrieve/README.md#retrievechunks) - Retrieve Chunks

#### [content.health](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/health/README.md)

* [getHealth](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/health/README.md#gethealth) - Check service health status

#### [content.import](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md)

* [createImportJob](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportjob) - Import content from external sources by creating an import job
* [getImportStatus](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#getimportstatus) - Get the current status of an import or validation job
* [createImportValidationJob](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportvalidationjob) - Validate content structure and format before import by creating an import validation job
* [cancelImport](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#cancelimport) - Cancel an import or validation job

#### [portal.article](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md)

* [getArticleById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlebyid) - Get Article by ID
* [getArticleByIdWithEditions](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlebyidwitheditions) - Get Article By ID with Editions
* [getArticleEditionDetails](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticleeditiondetails) - Get Article Edition Details
* [addToReply](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#addtoreply) - Add Article to Reply
* [addAsReference](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#addasreference) - Add as Reference
* [getArticlesInTopic](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlesintopic) - Get Articles in Topic
* [getArticleAttachmentById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticleattachmentbyid) - Get Article Attachment By ID
* [getAttachmentByIdInPortal](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getattachmentbyidinportal) - Get Article Attachment in Portal
* [getRelatedArticles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getrelatedarticles) - Get Related Articles
* [getAnnouncementArticles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getannouncementarticles) - Get Announcement Articles
* [getArticleRatings](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticleratings) - Get Article Ratings
* [rateArticle](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#ratearticle) - Rate an Article
* [getPendingComplianceArticles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getpendingcompliancearticles) - Get Pending Article Compliances
* [getAcknowledgedComplianceArticles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getacknowledgedcompliancearticles) - Get Acknowledged Article Compliances
* [complyArticle](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#complyarticle) - Comply With an Article
* [getMySubscription](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getmysubscription) - My Subscription
* [subscribeArticle](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#subscribearticle) - Subscribe to an Article
* [unsubscribeArticle](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#unsubscribearticle) - Unsubscribe to an Article
* [getArticlePermissionsById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlepermissionsbyid) - Get Article Permissions By ID
* [getArticlePersonalization](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlepersonalization) - Get Article Personalization Details

#### [portal.articlelists](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/articlelists/README.md)

* [getAllArticleLists](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/articlelists/README.md#getallarticlelists) - Get All Article Lists
* [getArticleListDetails](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/articlelists/README.md#getarticlelistdetails) - Get Article List by ID

#### [portal.attachment](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/attachment/README.md)

* [createSignedURL](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/attachment/README.md#createsignedurl) - Generate Signed URL to Upload API
* [uploadAttachment](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/attachment/README.md#uploadattachment) - Upload Attachment

#### [portal.bookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md)

* [addbookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#addbookmark) - Add a Bookmark
* [getbookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#getbookmark) - Get All Bookmarks for a Portal
* [deletebookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#deletebookmark) - Delete a Bookmark

#### [portal.connectorssearchevents](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md)

* [createSearchResultEventForConnectors](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createsearchresulteventforconnectors) - Event for Search Using Connectors
* [createViewedSearchResultsEventForConnectors](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createviewedsearchresultseventforconnectors) - Event for Viewed Search Results Using Connectors

#### [portal.escalation](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md)

* [startCustomerEscalation](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#startcustomerescalation) - Start Customer Escalation
* [searchPriorToEscalation](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#searchpriortoescalation) - Search Prior To Customer Escalation
* [completeCustomerEscalation](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#completecustomerescalation) - Complete Customer Escalation
* [avertCustomerEscalation](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#avertcustomerescalation) - Avert Customer Escalation

#### [portal.export](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/export/README.md)

* [exportContent](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/export/README.md#exportcontent) - Export Knowledge
* [exportStatus](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/export/README.md#exportstatus) - Get Export Job Status

#### [portal.federatedsearchevent](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/federatedsearchevent/README.md)

* [createFederatedSearchResultEvent](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/federatedsearchevent/README.md#createfederatedsearchresultevent) - Event For Viewed Federated Search Result

#### [portal.general](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md)

* [getAllPortals](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#getallportals) - Get All Portals
* [getMyPortals](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#getmyportals) - Get All Portals Accessible To User
* [getPortalDetailsById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#getportaldetailsbyid) - Get Portal Details By ID
* [getTagCategoriesForInterestForPortal](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#gettagcategoriesforinterestforportal) - Get Tag Categories for Interest for a Portal

#### [portal.guidedhelp](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md)

* [getAllCasebasesReleases](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallcasebasesreleases) - Get Available Casebases Releases
* [getCasebaseReleaseById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getcasebasereleasebyid) - Get Details of a Casebase Release
* [getClusterByCasebaseReleaseId](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getclusterbycasebasereleaseid) - Get Cluster Details of a Casebase Release
* [getAllProfilesInPortal](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallprofilesinportal) - Get All Profiles Available in Portal
* [startGHSearch](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#startghsearch) - Start a Guided Help Search
* [stepGHSearch](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#stepghsearch) - Perform a Step in a Guided Help Search
* [getAllCases](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallcases) - Get All Cases of a Cluster in Release
* [getCaseById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getcasebyid) - Get Details of a Case
* [acceptGHSolution](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#acceptghsolution) - Accept Solution
* [rejectGHSolution](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#rejectghsolution) - Reject Solution
* [createQuickpick](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#createquickpick) - Create Quickpick
* [getAllQuickPicks](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallquickpicks) - Get All Quickpicks for a Portal
* [restoreQuickpick](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#restorequickpick) - Resume a Quickpick

#### [portal.populararticles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/populararticles/README.md)

* [getpopulararticles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/populararticles/README.md#getpopulararticles) - Get Popular Articles

#### [portal.search](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/search/README.md)

* [aiSearch](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/search/README.md#aisearch) - Get the best search results for a user query

#### [portal.suggestion](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md)

* [makeSuggestion](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#makesuggestion) - Make a Suggestion
* [modifySuggestions](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#modifysuggestions) - Modify Suggestion
* [searchSuggestion](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#searchsuggestion) - Get Suggestion by Status
* [getSuggestion](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestion) - Get Suggestion by ID
* [deleteSuggestion](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#deletesuggestion) - Delete a Suggestion
* [getRelatedArticlesForSuggestion](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getrelatedarticlesforsuggestion) - Get Related Articles for Suggestion
* [getSuggestionComments](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestioncomments) - Get Suggestion Comments
* [getSuggestionAttachments](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestionattachments) - Get Suggestion Attachments
* [getSuggestionAttachmentById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestionattachmentbyid) - Get Suggestion Attachment by ID

#### [portal.topic](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md)

* [getTopicBreadcrumbForArticle](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#gettopicbreadcrumbforarticle) - Get Topic Breadcrumb for Article
* [getchildtopics](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#getchildtopics) - Get Immediate Child Topics
* [getancestortopics](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#getancestortopics) - Get All Ancestor Topics
* [getalltopics](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#getalltopics) - Get All Topics

#### [portal.userdetails](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userdetails/README.md)

* [getUserDetails](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userdetails/README.md#getuserdetails) - Get User Details

#### [portal.usermilestones](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/usermilestones/README.md)

* [getUserMilestones](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/usermilestones/README.md#getusermilestones) - Get User Milestones

#### [portal.userprofile](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userprofile/README.md)

* [getAllUserProfiles](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userprofile/README.md#getalluserprofiles) - Get All User Profiles Assigned to User
* [selectUserProfile](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userprofile/README.md#selectuserprofile) - Select User Profile

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`aiservicesAnswersGetBestAnswer`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/answers/README.md#getbestanswer) - Get the best answer for a user query
- [`aiservicesRetrieveRetrieveChunks`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/retrieve/README.md#retrievechunks) - Retrieve Chunks
- [`contentHealthGetHealth`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/health/README.md#gethealth) - Check service health status
- [`contentImportCancelImport`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#cancelimport) - Cancel an import or validation job
- [`contentImportCreateImportJob`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportjob) - Import content from external sources by creating an import job
- [`contentImportCreateImportValidationJob`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportvalidationjob) - Validate content structure and format before import by creating an import validation job
- [`contentImportGetImportStatus`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#getimportstatus) - Get the current status of an import or validation job
- [`portalArticleAddAsReference`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#addasreference) - Add as Reference
- [`portalArticleAddToReply`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#addtoreply) - Add Article to Reply
- [`portalArticleComplyArticle`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#complyarticle) - Comply With an Article
- [`portalArticleGetAcknowledgedComplianceArticles`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getacknowledgedcompliancearticles) - Get Acknowledged Article Compliances
- [`portalArticleGetAnnouncementArticles`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getannouncementarticles) - Get Announcement Articles
- [`portalArticleGetArticleAttachmentById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticleattachmentbyid) - Get Article Attachment By ID
- [`portalArticleGetArticleById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlebyid) - Get Article by ID
- [`portalArticleGetArticleByIdWithEditions`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlebyidwitheditions) - Get Article By ID with Editions
- [`portalArticleGetArticleEditionDetails`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticleeditiondetails) - Get Article Edition Details
- [`portalArticleGetArticlePermissionsById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlepermissionsbyid) - Get Article Permissions By ID
- [`portalArticleGetArticlePersonalization`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlepersonalization) - Get Article Personalization Details
- [`portalArticleGetArticleRatings`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticleratings) - Get Article Ratings
- [`portalArticleGetArticlesInTopic`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getarticlesintopic) - Get Articles in Topic
- [`portalArticleGetAttachmentByIdInPortal`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getattachmentbyidinportal) - Get Article Attachment in Portal
- [`portalArticleGetMySubscription`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getmysubscription) - My Subscription
- [`portalArticleGetPendingComplianceArticles`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getpendingcompliancearticles) - Get Pending Article Compliances
- [`portalArticleGetRelatedArticles`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#getrelatedarticles) - Get Related Articles
- [`portalArticlelistsGetAllArticleLists`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/articlelists/README.md#getallarticlelists) - Get All Article Lists
- [`portalArticlelistsGetArticleListDetails`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/articlelists/README.md#getarticlelistdetails) - Get Article List by ID
- [`portalArticleRateArticle`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#ratearticle) - Rate an Article
- [`portalArticleSubscribeArticle`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#subscribearticle) - Subscribe to an Article
- [`portalArticleUnsubscribeArticle`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/article/README.md#unsubscribearticle) - Unsubscribe to an Article
- [`portalAttachmentCreateSignedURL`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/attachment/README.md#createsignedurl) - Generate Signed URL to Upload API
- [`portalAttachmentUploadAttachment`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/attachment/README.md#uploadattachment) - Upload Attachment
- [`portalBookmarkAddbookmark`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#addbookmark) - Add a Bookmark
- [`portalBookmarkDeletebookmark`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#deletebookmark) - Delete a Bookmark
- [`portalBookmarkGetbookmark`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#getbookmark) - Get All Bookmarks for a Portal
- [`portalConnectorssearcheventsCreateSearchResultEventForConnectors`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createsearchresulteventforconnectors) - Event for Search Using Connectors
- [`portalConnectorssearcheventsCreateViewedSearchResultsEventForConnectors`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createviewedsearchresultseventforconnectors) - Event for Viewed Search Results Using Connectors
- [`portalEscalationAvertCustomerEscalation`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#avertcustomerescalation) - Avert Customer Escalation
- [`portalEscalationCompleteCustomerEscalation`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#completecustomerescalation) - Complete Customer Escalation
- [`portalEscalationSearchPriorToEscalation`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#searchpriortoescalation) - Search Prior To Customer Escalation
- [`portalEscalationStartCustomerEscalation`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/escalation/README.md#startcustomerescalation) - Start Customer Escalation
- [`portalExportExportContent`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/export/README.md#exportcontent) - Export Knowledge
- [`portalExportExportStatus`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/export/README.md#exportstatus) - Get Export Job Status
- [`portalFederatedsearcheventCreateFederatedSearchResultEvent`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/federatedsearchevent/README.md#createfederatedsearchresultevent) - Event For Viewed Federated Search Result
- [`portalGeneralGetAllPortals`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#getallportals) - Get All Portals
- [`portalGeneralGetMyPortals`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#getmyportals) - Get All Portals Accessible To User
- [`portalGeneralGetPortalDetailsById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#getportaldetailsbyid) - Get Portal Details By ID
- [`portalGeneralGetTagCategoriesForInterestForPortal`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/general/README.md#gettagcategoriesforinterestforportal) - Get Tag Categories for Interest for a Portal
- [`portalGuidedhelpAcceptGHSolution`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#acceptghsolution) - Accept Solution
- [`portalGuidedhelpCreateQuickpick`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#createquickpick) - Create Quickpick
- [`portalGuidedhelpGetAllCasebasesReleases`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallcasebasesreleases) - Get Available Casebases Releases
- [`portalGuidedhelpGetAllCases`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallcases) - Get All Cases of a Cluster in Release
- [`portalGuidedhelpGetAllProfilesInPortal`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallprofilesinportal) - Get All Profiles Available in Portal
- [`portalGuidedhelpGetAllQuickPicks`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getallquickpicks) - Get All Quickpicks for a Portal
- [`portalGuidedhelpGetCasebaseReleaseById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getcasebasereleasebyid) - Get Details of a Casebase Release
- [`portalGuidedhelpGetCaseById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getcasebyid) - Get Details of a Case
- [`portalGuidedhelpGetClusterByCasebaseReleaseId`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#getclusterbycasebasereleaseid) - Get Cluster Details of a Casebase Release
- [`portalGuidedhelpRejectGHSolution`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#rejectghsolution) - Reject Solution
- [`portalGuidedhelpRestoreQuickpick`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#restorequickpick) - Resume a Quickpick
- [`portalGuidedhelpStartGHSearch`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#startghsearch) - Start a Guided Help Search
- [`portalGuidedhelpStepGHSearch`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/guidedhelp/README.md#stepghsearch) - Perform a Step in a Guided Help Search
- [`portalPopulararticlesGetpopulararticles`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/populararticles/README.md#getpopulararticles) - Get Popular Articles
- [`portalSearchAiSearch`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/search/README.md#aisearch) - Get the best search results for a user query
- [`portalSuggestionDeleteSuggestion`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#deletesuggestion) - Delete a Suggestion
- [`portalSuggestionGetRelatedArticlesForSuggestion`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getrelatedarticlesforsuggestion) - Get Related Articles for Suggestion
- [`portalSuggestionGetSuggestion`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestion) - Get Suggestion by ID
- [`portalSuggestionGetSuggestionAttachmentById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestionattachmentbyid) - Get Suggestion Attachment by ID
- [`portalSuggestionGetSuggestionAttachments`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestionattachments) - Get Suggestion Attachments
- [`portalSuggestionGetSuggestionComments`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#getsuggestioncomments) - Get Suggestion Comments
- [`portalSuggestionMakeSuggestion`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#makesuggestion) - Make a Suggestion
- [`portalSuggestionModifySuggestions`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#modifysuggestions) - Modify Suggestion
- [`portalSuggestionSearchSuggestion`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/suggestion/README.md#searchsuggestion) - Get Suggestion by Status
- [`portalTopicGetalltopics`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#getalltopics) - Get All Topics
- [`portalTopicGetancestortopics`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#getancestortopics) - Get All Ancestor Topics
- [`portalTopicGetchildtopics`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#getchildtopics) - Get Immediate Child Topics
- [`portalTopicGetTopicBreadcrumbForArticle`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/topic/README.md#gettopicbreadcrumbforarticle) - Get Topic Breadcrumb for Article
- [`portalUserdetailsGetUserDetails`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userdetails/README.md#getuserdetails) - Get User Details
- [`portalUsermilestonesGetUserMilestones`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/usermilestones/README.md#getusermilestones) - Get User Milestones
- [`portalUserprofileGetAllUserProfiles`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userprofile/README.md#getalluserprofiles) - Get All User Profiles Assigned to User
- [`portalUserprofileSelectUserProfile`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/userprofile/README.md#selectuserprofile) - Select User Profile

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start File uploads [file-upload] -->
## File uploads

Certain SDK methods accept files as part of a multi-part request. It is possible and typically recommended to upload files as a stream rather than reading the entire contents into memory. This avoids excessive memory consumption and potentially crashing with out-of-memory errors when working with very large files. The following example demonstrates how to attach a file stream to a request.

> [!TIP]
>
> Depending on your JavaScript runtime, there are convenient utilities that return a handle to a file without reading the entire contents into memory:
>
> - **Node.js v20+:** Since v20, Node.js comes with a native `openAsBlob` function in [`node:fs`](https://nodejs.org/docs/latest-v20.x/api/fs.html#fsopenasblobpath-options).
> - **Bun:** The native [`Bun.file`](https://bun.sh/docs/api/file-io#reading-files-bun-file) function produces a file handle that can be used for streaming file uploads.
> - **Browsers:** All supported browsers return an instance to a [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File) when reading the value from an `<input type="file">` element.
> - **Node.js v18:** A file stream can be created using the `fileFrom` helper from [`fetch-blob/from.js`](https://www.npmjs.com/package/fetch-blob).

```typescript
import { Egain } from "@egain/egain-api-typescript";
import { openAsBlob } from "node:fs";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  await egain.portal.attachment.uploadAttachment({
    acceptLanguage: "en-US",
    signature: "<value>",
    requestBody: await openAsBlob("example.file"),
  });
}

run();

```
<!-- End File uploads [file-upload] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  }, {
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`EgainError`](./src/models/errors/egainerror.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                                                             |
| ------------------- | ---------- | --------------------------------------------------------------------------------------- |
| `error.message`     | `string`   | Error message                                                                           |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                                                      |
| `error.headers`     | `Headers`  | HTTP response headers                                                                   |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned.                                  |
| `error.rawResponse` | `Response` | Raw HTTP response                                                                       |
| `error.data$`       |            | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```typescript
import { Egain } from "@egain/egain-api-typescript";
import * as errors from "@egain/egain-api-typescript/models/errors";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  try {
    const result = await egain.content.import.createImportJob({
      dataSource: {
        type: "AWS S3 bucket",
        path: "s3://mybucket/myfolder/",
        region: "us-east-1",
        credentials: {},
      },
      operation: "import",
      scheduleTime: {
        date: new Date("2024-03-01T10:00:00.000Z"),
      },
    });

    console.log(result);
  } catch (error) {
    // The base class for HTTP error responses
    if (error instanceof errors.EgainError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);

      // Depending on the method different errors may be thrown
      if (error instanceof errors.WSErrorCommon) {
        console.log(error.data$.code); // string
        console.log(error.data$.developerMessage); // string
        console.log(error.data$.details); // WSErrorCommonDetail[]
        console.log(error.data$.userMessage); // string
      }
    }
  }
}

run();

```

### Error Classes
**Primary errors:**
* [`EgainError`](./src/models/errors/egainerror.ts): The base class for HTTP error responses.
  * [`WSErrorCommon`](./src/models/errors/wserrorcommon.ts): Bad Request. *

<details><summary>Less common errors (8)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`EgainError`](./src/models/errors/egainerror.ts)**:
* [`SchemasWSErrorCommon`](./src/models/errors/schemaswserrorcommon.ts): Preconditions failed. Status code `412`. Applicable to 2 of 79 methods.*
* [`ServiceUnavailableError`](./src/models/errors/serviceunavailableerror.ts): ## Service is Unhealthy  The Import Content service is experiencing critical issues and may not be able to process requests properly.  **Health Status Details:** - **Overall Status**: Service is unhealthy and may not function correctly  **Response Information:** - **Status**: Current health state (unhealthy) - **Timestamp**: When health check was performed - **Version**: Current API version - **Issues**: List of detected health problems. Status code `503`. Applicable to 1 of 79 methods.*
* [`ResponseValidationError`](./src/models/errors/responsevalidationerror.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>

\* Check [the method documentation](#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `serverURL: string` optional parameter when initializing the SDK client instance. For example:
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  serverURL: "https://${API_DOMAIN}/knowledge/portalmgr/v4",
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  });

  console.log(result);
}

run();

```

### Override Server URL Per-Operation

The server URL can also be overridden on a per-operation basis, provided a server list was specified for the operation. For example:
```typescript
import { Egain } from "@egain/egain-api-typescript";

const egain = new Egain({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.retrieve.retrieveChunks({
    q: "fair lending",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-3210",
    language: "en-US",
    filterTags: {
      "PROD-1234": [
        "PROD-2000",
        "PROD-2003",
      ],
      "PROD-2005": [
        "PROD-2007",
      ],
    },
    retrieveRequest: {
      channel: {
        name: "Eight Bank Website",
      },
    },
  }, {
    serverURL: "https://${API_DOMAIN}/core/aiservices/v4",
  });

  console.log(result);
}

run();

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to use the `"beforeRequest"` hook to to add a
custom header and a timeout to requests and how to use the `"requestError"` hook
to log errors:

```typescript
import { Egain } from "@egain/egain-api-typescript";
import { HTTPClient } from "@egain/egain-api-typescript/lib/http";

const httpClient = new HTTPClient({
  // fetcher takes a function that has the same signature as native `fetch`.
  fetcher: (request) => {
    return fetch(request);
  }
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new Egain({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { Egain } from "@egain/egain-api-typescript";

const sdk = new Egain({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `EGAIN_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=@egain/egain-api-typescript&utm_campaign=typescript)
