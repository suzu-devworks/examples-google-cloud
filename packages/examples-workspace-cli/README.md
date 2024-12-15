# examples-workspace-cli

This is an example of a client that uses Python to control Google Workspace.

## Table of Contents <!-- omit in toc -->

- [examples-workspace-cli](#examples-workspace-cli)
  - [Examples](#examples)
    - [Getting started](#getting-started)
    - [Google Workspace apps for Python](#google-workspace-apps-for-python)
  - [Learn more](#learn-more)
  - [Configure Google Cloud API](#configure-google-cloud-api)
    - [Enable APIs](#enable-apis)
    - [When use service account (silent login)](#when-use-service-account-silent-login)
    - [When use user account (OAuth login)](#when-use-user-account-oauth-login)
  - [User credentials provided by using the gcloud CLI(OPTIONAL)](#user-credentials-provided-by-using-the-gcloud-clioptional)
  - [Development](#development)
    - [How the project was initialized](#how-the-project-was-initialized)

## Examples

### Getting started

Install dependency packages and install myself locally:

```shell
uv sync --project packages/examples-workspace-cli
```

Show help command:

```shell
examples-workspace-cli -h
```

### Google Workspace apps for Python

- [`auth` - Google Auth](./src/examples_workspace_cli/auth/README.md)
- [`drive` - Google Drive API example](./src/examples_workspace_cli/drive/README.md)
- [`docs` - Google Docs API example](./src/examples_workspace_cli/docs/README.md)
- [`sheets` - Google Sheets API example](./src/examples_workspace_cli/sheets/README.md)
- [`calendar` - Google Calendar API example](./src/examples_workspace_cli/calendar/README.md)
- [`chat` - Google Chat API example](./src/examples_workspace_cli/chat/README.md)
- [`gmail` - Google Gmail API example](./src/examples_workspace_cli/gmail/README.md)

## Learn more

- [Enhance Google Workspace apps](https://developers.google.com/workspace?hl=ja)

## Configure Google Cloud API

Goto google cloud console:

- <https://console.cloud.google.com/welcome>

### Enable APIs

1. APIs & Services > Library
2. Enable the following libraries:
   - [Google Drive API]
   - [Google Docs API]
   - [Google Sheets API]
   - [Google Calendar API]
   - [Google Chat API]
   - [Gmail API]

### When use service account (silent login)

1. IAM and Admin > Service Accounts > CREATE SERVICE ACCOUNT
   > - Service account details:  
   >   Input service account id.
   > - Grant this service account access to project:  
   >   Select Editor role.
   > - DONE
2. select created service account
3. service account > KEYS > ADD KEY(Create new key)
   > - type(JSON) > Create
4. json file will be downloaded automatically.
5. Rename the file to `service_account.json` and add it to your project
6. _Grant permissions for Google services to service accounts_

### When use user account (OAuth login)

1. APIs & Services > OAuth consent screen
   > - User type: External > create
   > - OAuth consent screen:
   >   - App name: any name
   >   - User support email: your email
   >   - Email addresses: your email
   > - Test user:
   >   - ADD USERS: your email.
2. Credentials > CREATE CREDENTIALS > OAuth client ID
   > - Select Application Type: Desktop app
   > - CREATE
3. Download json file.
4. Rename the file to `credentials.json` and add it to your project

## User credentials provided by using the gcloud CLI(OPTIONAL)

Download gcloud CLI:

- <https://cloud.google.com/sdk/docs/install?hl=ja>

Initialize the CLI:

```shell
gcloud init
```

Select the project you created in the Google Cloud Console.

```console
Pick cloud project to use: 
 [1] examples-py-gcloud
 [2] Enter a project ID
 [3] Create a new project
Please enter numeric choice or text value (must exactly match list item):  1
```

Provides authentication information to the Application Default Credentials (ADC):

```shell
gcloud auth application-default login --client-id-file=/workspaces/examples-py-gcloud/credentials.json --scopes=https://www.googleapis.com/auth/cloud-platform 
```

## Development

### How the project was initialized

This project was initialized with the following command:

```shell
uv init --package packages/examples-workspace-cli
uv add --project packages/examples-workspace-cli --dev pytest pytest-asyncio pytest-cov
uv add --project packages/examples-workspace-cli pyyaml
uv add --project packages/examples-workspace-cli --dev types-PyYAML

uv add --project packages/examples-workspace-cli google-api-python-client google-auth-httplib2 google-auth-oauthlib
uv add --project packages/examples-workspace-cli google-apps-chat
uv add --project packages/examples-workspace-cli gspread
```
