# Postman Collection for Messenger Platform &nbsp;&nbsp;&nbsp; [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/a760368515fa96cedcb6#?env%5BMessenger%20Platform%20Environment%20Variables%5D=W3sidHlwZSI6InRleHQiLCJlbmFibGVkIjp0cnVlLCJrZXkiOiJTRVRfRU5WIiwidmFsdWUiOiJUUlVFIn0seyJ0eXBlIjoidGV4dCIsImVuYWJsZWQiOnRydWUsImtleSI6IlBBR0VfVE9LRU4iLCJ2YWx1ZSI6IllPVVIgUEFHRSBBQ0NFU1MgVE9LRU4ifSx7InR5cGUiOiJ0ZXh0IiwiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiUFNJRCIsInZhbHVlIjoiWU9VUiBQQUdFLVNDT1BFRCBVU0VSIElEIn0seyJ0eXBlIjoidGV4dCIsImVuYWJsZWQiOnRydWUsImtleSI6IkFTSUQiLCJ2YWx1ZSI6IklEIE1BVENISU5HIC0gQVBQLVNDT1BFRCBVU0VSIElEIn0seyJ0eXBlIjoidGV4dCIsImVuYWJsZWQiOnRydWUsImtleSI6IkFQUF9JRCIsInZhbHVlIjoiSUQgTUFUQ0hJTkcgLSBBUFAgSUQifSx7InR5cGUiOiJ0ZXh0IiwiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiQVBQX1NFQ1JFVCIsInZhbHVlIjoiSUQgTUFUQ0hJTkcgLSBBUFAgU0VDUkVUIn0seyJ0eXBlIjoidGV4dCIsImVuYWJsZWQiOnRydWUsImtleSI6IkFQUF9JRF9QUklNQVJZIiwidmFsdWUiOiJIQU5ET1ZFUiBQUk9UT0NPTCAtIFBSSU1BUlkgUkVDRUlWRVIgQVBQIElEIn0seyJ0eXBlIjoidGV4dCIsImVuYWJsZWQiOnRydWUsImtleSI6IkFQUF9JRF9TRUNPTkRBUlkiLCJ2YWx1ZSI6IkhBTkRPVkVSIFBST1RPQ09MIC0gU0VDT05EQVJZIFJFQ0VJVkVSIEFQUCBJRCJ9LHsidHlwZSI6InRleHQiLCJlbmFibGVkIjp0cnVlLCJrZXkiOiJFWFRFTlNJT05TX1VSTCIsInZhbHVlIjoiQSBVUkwgVE8gVVNFIEZPUiBNRVNTRU5HRVIgRVhURU5TSU9OUyJ9LHsidHlwZSI6InRleHQiLCJlbmFibGVkIjp0cnVlLCJrZXkiOiJXSVRfVE9LRU4iLCJ2YWx1ZSI6IkJVSUxULUlOIE5MUCAtIFdJVCBTRVJWRVIgQUNDRVNTIFRPS0VOIn1d)

___Collection Last Updated: 12/28/17 - Fixed Get Static Code___

This is a [Postman](https://getpostman.com) collection that covers pretty much every API request available for the Messenger Platform. This collection should be useful for getting started working with your bot to try out features and send all the different message types. You can also use it once you are in production to send messages!

## Using this Collection

### Basic Usage

To use this collection, do the following:

1. [Download Postman](https://www.getpostman.com)
2. Click the 'Run in Postman' button at the top of this Readme to import the collection and a 'Messenger Platform Environment Variables' environment into Postman.
3. Add the [appropriate environment variables](#vars) to the 'Messenger Platform Environment Variables' environment.
4. Run some of the API calls.

### Collection Runner

Want to see evvvveeerrryyttthhhiinnnggg run? Do the following:

1. Set the [appropriate environment variables](#vars) in the 'Messenger Platform Environment Variables' environment.
2. Open the Postman collection runner.
3. Select the 'Messenger Platform' collection and 'Messenger Platform Environment Variables' environment.
4. Click the 'Run' button.

This is pretty cool because your environment will also be auto-populated with various responses from the API that are needed for other calls.

**DANGER, WILL ROBINSON**: Postman will run all of the API calls in order. This means that if you re-arrange them in the collection, a full test run may not work as expected.

### Updating this Collection

**Postman collections do not automatically sync when they are updated.** So if you like this, you should come back periodically to download it. I'll try to keep a 'last updated' date at the top of this readme and maybe some kind of changelog.

## <a id="vars"></a>Environment Variables

This collection makes liberal use of [Postman environment variables](https://www.getpostman.com/docs/postman/environments_and_globals/manage_environments) to automate API requests to the greatest extent possible. Basically, anytime you see `{{SOME_VAR_NAME}}` in a request body or URI that's a Postman env var. 

When you load this collection into Postman, it will also load a 'Messenger Platform Environment Variables' environment that includes all the possible env vars used by this collection.

### Required Environment Variables

**At a minimum** you should set these environment variables, since they are needed for almost all Messenger Platform API requests, especially message sends.

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `PSID` | String | A page-scoped ID | Specifies the user to target. This will be used as the default user for all requests. To get this, send a message to your bots and extract the `id` property from the `messages` webhook event. |
| `PAGE_TOKEN` | String | Your Page access token  | Almost all API requests. Available in the 'Token Generation' section of your app's Messenger settings. |
| `SET_ENV`| Boolean | Sets whether other env vars will be automatically set from API responses when you use Postman's collection runner. | This is a convenience so that you don't have to manually set a bunch of IDs for all the different API requests. |

**If you want to run the whoooollleeee collection** in the collection runner, you'll also need to set these:

- [Handover protocol](#hop)
- [ID Matching](#id-matching)
- [Wit.ai](#wit)
- [Messenger Profile](#profile)

### Optional Environment Variables

Many of the optional vars will be set for you if you set the `SET_ENV` env var to `TRUE` and run Postman's collection runner. You can also set these manually in each call if you want.

#### Reusable Assets

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `IMAGE_ATTACHMENT_ID` | String | An `attachment_id` of an uploaded image | The `attachment_id` to use for message sends with an image. |
| `VIDEO_ATTACHMENT_ID` | String | An `attachment_id` of an uploaded video | The `attachment_id` to use for message sends with a video. |

#### <a id="hop"></a>Handover Protocol

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `APP_ID_PRIMARY` | String | An app ID | The app ID for the Facebook app you want to use as the Primary Receiver for your bot. |
| `APP_ID_SECONDARY` | String | An app ID | The app ID for the Facebook app you want to use as the Secondary Primary Receiver for your bot. |

#### Broadcast API

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `MESSAGE_CREATIVE_ID_ALL` | String | A `message_creative_id` | The `message_creative_id` of a message creative to broadcast to all open conversations. |
| `MESSAGE_CREATIVE_ID_TARGETED` | String | A `message_creative_id` | The `message_creative_id` of a message creative to broadcast to open conversations associated with a custom label. |
| `REACH_ESTIMATION_ID` | String | A `reach_estimation_id` | The `reach_estimation_id` to start a reach estimation for. |
| `CUSTOM_LABEL_ID` | String | A `custom_label_id` | The `custom_label_id` to associate with PSIDs or to target a broadcast to. When `SET_ENV` is set to `TRUE`, the value will be 'custom_label_<timestamp>'. |
| `CUSTOM_LABEL_ID_TO_DELETE` | String | A `custom_label_id` | When `SET_ENV` is set to `TRUE`, this is set when the 'Create Custom Label' call happens. It is deleted when 'Delete Custom Label' call happens.  |

#### <a id="id-matching"></a>ID Matching

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `ASID`  | String | A user's app-scoped ID | The app-scoped ID to match with the ID Matching API. |
| `APP_TOKEN` | String | An app token | The app token to use with the ID Matching API. |
| `APP_SECRET` | String | An app secret | The app secret to use with the ID Matching API. |

#### <a id="wit"></a>Built-in NLP

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `WIT_TOKEN` | String | A Wit.ai server access token | Connects your Messenger bot to a Wit.ai custom model. Available in the settings for your [Wit.ai](https://wit.ai/) app. |

#### <a id="profile"></a>Messenger Profile API

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `EXTENSIONS_URL` | String | A HTTPS URL | Used for Messenger Profile API calls that require a URL. |

## Behold!

<p align="center">
<a href="http://bit.ly/messenger-postman-video"><img src="https://github.com/amuramoto/messenger-platform-postman-collection/blob/master/videoimg.jpg?raw=true" />
  </p>
<p align="center">
<a href="http://bit.ly/messenger-postman-video">
(Click to see the YouTube video)</a>
</p>

## Useful Resources

Never used Postman or the Messenger Platform before? Here's some useful links to get you started and to get help when you have questions or run into problems. <3

#### Messenger Platform

- [Messenger Platform Developer Group](https://facebook.com/groups/messengerplatform/)

- [Facebook Messenger Bot Tag on Stack Overflow](https://stackoverflow.com/questions/tagged/facebook-messenger-bot)

- [Messenger Platform Update Bot](https://m.me/messengerplatform)

- [Messenger Platform Docs](https://developers.facebook.com/docs/messenger-platform)

- [Messenger Platform Quick Start Tutorial](https://developers.facebook.com/docs/messenger-platform/getting-started/quick-start)

#### Postman

- [Download Postman](https://www.getpostman.com/postman)

- [Postman Collection Docs](https://www.getpostman.com/docs/postman/collections/managing_collections)

- [Postman Environment Docs](https://www.getpostman.com/docs/postman/environments_and_globals/manage_environments)

- [Postman Scripting Docs](https://www.getpostman.com/docs/postman/scripts/intro_to_scripts)

- [Postman Scripting API Reference](https://www.getpostman.com/docs/postman/scripts/postman_sandbox_api_reference)
