# Standalone Functions

> [!NOTE]
> This section is useful if you are using a bundler and targetting browsers and
> runtimes where the size of an application affects performance and load times. 

Every method in this SDK is also available as a standalone function. This
alternative API is suitable when targetting the browser or serverless runtimes
and using a bundler to build your application since all unused functionality
will be tree-shaken away. This includes code for unused methods, Zod schemas,
encoding helpers and response handlers. The result is dramatically smaller
impact on the application's final bundle size which grows very slowly as you use
more and more functionality from this SDK.

Calling methods through the main SDK class remains a valid and generally more
more ergonomic option. Standalone functions represent an optimisation for a
specific category of applications.

## Example

```typescript
import { EgainCore } from "@egain/egain-api-typescript/core.js";
import { aiservicesRetrieveRetrieveChunks } from "@egain/egain-api-typescript/funcs/aiservicesRetrieveRetrieveChunks.js";

// Use `EgainCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const egain = new EgainCore({
  accessToken: process.env["EGAIN_ACCESS_TOKEN"] ?? "",
});

async function run() {
  const res = await aiservicesRetrieveRetrieveChunks(egain, {
    q: "fair lending",
    portalID: "PROD-1000",
    dollarFilterUserProfileID: "PROD-3210",
    language: "en-US",
    dollarFilterTags: {
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
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("aiservicesRetrieveRetrieveChunks failed:", res.error);
  }
}

run();
```

## Result types

Standalone functions differ from SDK methods in that they return a
`Result<Value, Error>` type to capture _known errors_ and document them using
the type system. By avoiding throwing errors, application code maintains clear
control flow and error-handling become part of the regular flow of application
code.

> We use the term "known errors" because standalone functions, and JavaScript
> code in general, can still throw unexpected errors such as `TypeError`s,
> `RangeError`s and `DOMException`s. Exhaustively catching all errors may be
> something this SDK addresses in the future. Nevertheless, there is still a lot
> of benefit from capturing most errors and turning them into values.

The second reason for this style of programming is because these functions will
typically be used in front-end applications where exception throwing is
sometimes discouraged or considered unidiomatic. React and similar ecosystems
and libraries tend to promote this style of programming so that components
render useful content under all states (loading, success, error and so on).

The general pattern when calling standalone functions looks like this:

```typescript
import { Core } from "<sdk-package-name>";
import { fetchSomething } from "<sdk-package-name>/funcs/fetchSomething.js";

const client = new Core();

async function run() {
  const result = await fetchSomething(client, { id: "123" });
  if (!result.ok) {
    // You can throw the error or handle it. It's your choice now.
    throw result.error;
  }

  console.log(result.value);
}

run();
```

Notably, `result.error` above will have an explicit type compared to a try-catch
variation where the error in the catch block can only be of type `unknown` (or
`any` depending on your TypeScript settings).