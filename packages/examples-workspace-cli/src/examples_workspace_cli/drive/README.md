# `drive` - Google Drive API example

## Table of Contents <!-- omit in toc -->

- [`drive` - Google Drive API example](#drive---google-drive-api-example)
  - [examples](#examples)
    - [`quickstart`](#quickstart)
    - [`list`](#list)

## examples

### `quickstart`

- [Python quickstart - Google](https://developers.google.com/docs/api/quickstart/python?hl=ja)
- [quickstart - Github](https://github.com/googleworkspace/python-samples/tree/main/docs/quickstart)

Need a `credentials.json` file in the current directory.

```shell
examples-workspace-cli drive quickstart
```

### `list`

Displays a list of drives.

```shell
examples-workspace-cli drive list
```

When specifying the parent directory:

```shell
examples-workspace-cli drive list -d {directory id}
```
