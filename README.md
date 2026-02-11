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

Knowledge Portal Manager APIs: 
### License
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

For supported JavaScript runtimes, please consult [RUNTIMES.md](https://github.com/eGain/egain-api-typescript/blob/main/RUNTIMES.md).
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
    q: "What is a loan?",
    portalID: "PROD-1000",
    filterUserProfileID: "PROD-1030",
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
      eventId: "6154589f-b43f-4471-b2c7-92c6c888a664",
      clientSessionId: "6154589f-b43f-4471-b2c7-92c6c888a643",
      sessionId: "6154589f-b43f-4471-b2c7-92c6c888a689",
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
  const result = await egain.aiservices.prompt.executePrompt({
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
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

* [getBestAnswer](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/answers/README.md#getbestanswer) - Generate an Answer

#### [aiservices.prompt](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/aiservicesprompt/README.md)

* [executePrompt](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/aiservicesprompt/README.md#executeprompt) - Execute a predefined prompt

#### [aiservices.retrieve](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/retrieve/README.md)

* [retrieveChunks](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/retrieve/README.md#retrievechunks) - Retrieve Chunks

#### [content.import](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md)

* [createImportJob](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportjob) - Create Import Job
* [getImportStatus](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#getimportstatus) - Get Job Status
* [createImportValidationJob](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportvalidationjob) - Create Validation Job
* [cancelImport](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#cancelimport) - Cancel Job

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

#### [portal.bookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md)

* [addbookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#addbookmark) - Add a Bookmark
* [getbookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#getbookmark) - Get All Bookmarks for a Portal
* [deletebookmark](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#deletebookmark) - Delete a Bookmark

#### [portal.connectorssearchevents](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md)

* [createSearchResultEventForConnectors](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createsearchresulteventforconnectors) - Event for Search Using Connectors
* [createViewedSearchResultsEventForConnectors](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createviewedsearchresultseventforconnectors) - Event for Viewed Search Results Using Connectors

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

* [aiSearch](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/search/README.md#aisearch) - Hybrid Search

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

### [prompt](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/prompt/README.md)

* [getPromptTemplates](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/prompt/README.md#getprompttemplates) - Get Prompt Templates
* [getPromptTemplateById](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/prompt/README.md#getprompttemplatebyid) - Get Prompt Template By ID

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](https://github.com/eGain/egain-api-typescript/blob/main/FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`aiservicesAnswersGetBestAnswer`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/answers/README.md#getbestanswer) - Generate an Answer
- [`aiservicesPromptExecutePrompt`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/aiservicesprompt/README.md#executeprompt) - Execute a predefined prompt
- [`aiservicesRetrieveRetrieveChunks`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/retrieve/README.md#retrievechunks) - Retrieve Chunks
- [`contentImportCancelImport`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#cancelimport) - Cancel Job
- [`contentImportCreateImportJob`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportjob) - Create Import Job
- [`contentImportCreateImportValidationJob`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#createimportvalidationjob) - Create Validation Job
- [`contentImportGetImportStatus`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/import/README.md#getimportstatus) - Get Job Status
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
- [`portalBookmarkAddbookmark`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#addbookmark) - Add a Bookmark
- [`portalBookmarkDeletebookmark`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#deletebookmark) - Delete a Bookmark
- [`portalBookmarkGetbookmark`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/bookmark/README.md#getbookmark) - Get All Bookmarks for a Portal
- [`portalConnectorssearcheventsCreateSearchResultEventForConnectors`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createsearchresulteventforconnectors) - Event for Search Using Connectors
- [`portalConnectorssearcheventsCreateViewedSearchResultsEventForConnectors`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/connectorssearchevents/README.md#createviewedsearchresultseventforconnectors) - Event for Viewed Search Results Using Connectors
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
- [`portalSearchAiSearch`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/search/README.md#aisearch) - Hybrid Search
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
- [`promptGetPromptTemplateById`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/prompt/README.md#getprompttemplatebyid) - Get Prompt Template By ID
- [`promptGetPromptTemplates`](https://github.com/eGain/egain-api-typescript/blob/main/docs/sdks/prompt/README.md#getprompttemplates) - Get Prompt Templates

</details>
<!-- End Standalone functions [standalone-funcs] -->

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
  const result = await egain.aiservices.prompt.executePrompt({
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
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
  const result = await egain.aiservices.prompt.executePrompt({
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
    },
  });

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`EgainError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/egainerror.ts) is the base class for all HTTP error responses. It has the following properties:

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
    const result = await egain.aiservices.prompt.executePrompt({
      promptId: "<id>",
      executePrompt: {
        department: "Service",
        languageCode: "en-US",
        clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
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
      if (error instanceof errors.BadRequestError) {
        console.log(error.data$.code); // number
        console.log(error.data$.developerMessage); // string
      }
    }
  }
}

run();

```

### Error Classes
**Primary errors:**
* [`EgainError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/egainerror.ts): The base class for HTTP error responses.
  * [`WSErrorCommon`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/wserrorcommon.ts): Bad Request. *

<details><summary>Less common errors (8)</summary>

<br />

**Network errors:**
* [`ConnectionError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`EgainError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/egainerror.ts)**:
* [`SchemasWSErrorCommon`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/schemaswserrorcommon.ts): Not acceptable. Applicable to 4 of 76 methods.*
* [`BadRequestError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/badrequesterror.ts): Bad Request. Status code `400`. Applicable to 1 of 76 methods.*
* [`ResponseValidationError`](https://github.com/eGain/egain-api-typescript/blob/main/src/models/errors/responsevalidationerror.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

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
  serverURL: "https://api.aidev.egain.cloud/knowledge/portalmgr/v4",
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const result = await egain.aiservices.prompt.executePrompt({
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
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
  const result = await egain.aiservices.prompt.executePrompt({
    promptId: "<id>",
    executePrompt: {
      department: "Service",
      languageCode: "en-US",
      clientSessionId: "123e4567-e89b-12d3-a456-426614174000",
    },
  }, {
    serverURL: "https://api.aidev.egain.cloud/core/aiservices/v4",
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
