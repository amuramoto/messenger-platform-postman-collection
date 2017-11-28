# messenger-platform-postman-collection-
A delicious Postman collection for all your Messenger Platform needs.

## Required Environment Variables

**At a minimum** you should set these environment variables, since they are needed for almost all Messenger Platform API requests, especially message sends.

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `PSID` | String | A page-scoped ID. This will be used as the default user for all requests. | Specifies the user to target. |
| `PAGE_TOKEN` | String | Your Page access token. | Almost all API requests. |
| `SET_ENV`| Boolean | Sets whether other env vars will be automatically set from API responses when you use Postman's collection runner. | Almost all API requests. |

## Optional Environment Variables

### Credentials

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `ASID`  | String | | |
| `APP_TOKEN` | String | | |
| `APP_SECRET` | String | | |
| `APP_SECRET_PROOF` | String | | |

### Built-in NLP

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `WIT_TOKEN` | String | | |

### Handover Protocol

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `APP_ID_PRIMARY` | String | | |
| `APP_ID_SECONDARY` | String | | |

### Broadcast API

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `MESSAGE_CREATIVE_ID_ALL` | String | | |
| `MESSAGE_CREATIVE_ID_TARGETED` | String | | |
| `REACH_ESTIMATION_ID` | String | | |
| `CUSTOM_LABEL_ID` | String | | |

### Reusable Assets

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `IMAGE_ATTACHMENT_ID` | String | | |
| `VIDEO_ATTACHMENT_ID` | String | | |
