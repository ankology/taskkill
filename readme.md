# taskkill

> Wrapper for the Windows [`taskkill`](https://technet.microsoft.com/en-us/library/bb491009.aspx) command. Ends one or more tasks or processes.

## Install

```
$ npm install taskkill
```

## Usage

```js
import {taskkill, taskkillSync} from 'taskkill';

await taskkill([pid, pid2]); //Async usage
taskkillSync([pid, pid2]); //Sync usage
```

## API

See the [`taskkill` docs](https://technet.microsoft.com/en-us/library/bb491009.aspx) for more.

The package export two methods **with same arguments usage**:

### taskkill(input, options?)

Default export and async execution. Returns a `Promise`.

### taskkillSync(input, options?)

Sync execution. Returns or throws.

### Arguments

#### input

Type: `string | number | string[] | number[]`

One or more process IDs or image names, but not mixed.

#### options

The `system`, `username`, `password` options are mutually inclusive.

##### system

Type: `string`

Name or IP address of a remote computer (do not use backslashes). The default is the local computer.

##### username

Type: `string`

A user specified by `User` or `Domain\User`.

The default is the permissions of the current logged on user on the computer issuing the command.

##### password

Type: `string`

Password of the user account for the specified `username`.

##### filter

Type: `string`

Types of processes to include or exclude from termination.

See the [`taskkill` docs](https://technet.microsoft.com/en-us/library/bb491009.aspx) for supported filters.

##### force

Type: `boolean`

Forcefully terminate processes. Ignored for remote processes as all remote processes are forcefully terminated.

##### tree

Type: `boolean`

Terminate all child processes along with the parent process, commonly known as a tree kill.

## Related

- [tasklist](https://github.com/sindresorhus/tasklist) - Wrapper for the Windows `tasklist` command
- [fkill](https://github.com/sindresorhus/fkill) - Force kill processes, cross-platform

## Maintainers

- [Sindre Sorhus](https://sindresorhus.com)
- [Mark Tiedemann](https://marksweb.site)
