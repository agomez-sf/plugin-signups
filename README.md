# plugin-signups

[![NPM](https://img.shields.io/npm/v/@salesforce/plugin-signups.svg?label=@salesforce/plugin-signups)](https://www.npmjs.com/package/@salesforce/plugin-signups) [![CircleCI](https://circleci.com/gh/salesforcecli/plugin-signups/tree/main.svg?style=shield)](https://circleci.com/gh/salesforcecli/plugin-signups/tree/main) [![Downloads/week](https://img.shields.io/npm/dw/@salesforce/plugin-signups.svg)](https://npmjs.org/package/@salesforce/plugin-signups) [![License](https://img.shields.io/badge/License-BSD%203--Clause-brightgreen.svg)](https://raw.githubusercontent.com/salesforcecli/plugin-signups/main/LICENSE.txt)

## Learn about the plugin-signups

Salesforce CLI plugins are based on the [oclif plugin framework](<(https://oclif.io/docs/introduction.html)>). Read the [plugin developer guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_plugins.meta/sfdx_cli_plugins/cli_plugins_architecture_sf_cli.htm) to learn about Salesforce CLI plugin development.

This repository contains a lot of additional scripts and tools to help with general Salesforce node development and enforce coding standards. You should familiarize yourself with some of the [node developer packages](https://github.com/forcedotcom/sfdx-dev-packages/) used by Salesforce. There is also a default circleci config using the [release management orb](https://github.com/forcedotcom/npm-release-management-orb) standards.

Additionally, there are some additional tests that the Salesforce CLI will enforce if this plugin is ever bundled with the CLI. These test are included by default under the `posttest` script and it is recommended to keep these tests active in your plugin, regardless if you plan to have it bundled.

# Everything past here is only a suggestion as to what should be in your specific plugin's description

This plugin is bundled with the [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli). For more information on the CLI, read the [getting started guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_intro.htm).

We always recommend using the latest version of these commands bundled with the CLI, however, you can install a specific version or tag if needed.

## Install

```bash
sfdx plugins:install signups@x.y.z
```

## Issues

Please report any issues at https://github.com/forcedotcom/cli/issues

## Contributing

1. Please read our [Code of Conduct](CODE_OF_CONDUCT.md)
2. Create a new issue before starting your project so that we can keep track of
   what you are trying to add/fix. That way, we can also offer suggestions or
   let you know if there is already an effort in progress.
3. Fork this repository.
4. [Build the plugin locally](#build)
5. Create a _topic_ branch in your fork. Note, this step is recommended but technically not required if contributing using a fork.
6. Edit the code in your fork.
7. Write appropriate tests for your changes. Try to achieve at least 95% code coverage on any new code. No pull request will be accepted without unit tests.
8. Sign CLA (see [CLA](#cla) below).
9. Send us a pull request when you are done. We'll review your code, suggest any needed changes, and merge it in.

### CLA

External contributors will be required to sign a Contributor's License
Agreement. You can do so by going to https://cla.salesforce.com/sign-cla.

### Build

To build the plugin locally, make sure to have yarn installed and run the following commands:

```bash
# Clone the repository
git clone git@github.com:salesforcecli/plugin-signups

# Install the dependencies and compile
yarn install
yarn build
```

To use your plugin, run using the local `./bin/run` or `./bin/run.cmd` file.

```bash
# Run using local run file.
./bin/run force:org:shape
```

There should be no differences when running via the Salesforce CLI or using the local run file. However, it can be useful to link the plugin to do some additional testing or run your commands from anywhere on your machine.

```bash
# Link your plugin to the sfdx cli
sfdx plugins:link .
# To verify
sfdx plugins
```

## Commands

<!-- commands -->

- [`sfdx force:org:shape:create [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceorgshapecreate--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)
- [`sfdx force:org:shape:delete [-p] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceorgshapedelete--p--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)
- [`sfdx force:org:shape:list [--verbose] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceorgshapelist---verbose---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)

## `sfdx force:org:shape:create [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

Create a scratch org configuration (shape) based on the specified source org

```
USAGE
  $ sfdx force:org:shape:create [-u <string>] [--apiversion <string>] [--json] [--loglevel
    trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

FLAGS
  -u, --targetusername=<value>                                                      username or alias for the target
                                                                                    org; overrides default target org
  --apiversion=<value>                                                              override the api version used for
                                                                                    api requests made by this command
  --json                                                                            format output as json
  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

DESCRIPTION
  Create a scratch org configuration (shape) based on the specified source org

EXAMPLES
  $ sfdx force:org:shape:create -u me@my.org

  $ sfdx force:org:shape:create -u me@my.org --json --loglevel debug
```

_See code: [src/commands/force/org/shape/create.ts](https://github.com/salesforcecli/plugin-signups/blob/v1.0.0/src/commands/force/org/shape/create.ts)_

## `sfdx force:org:shape:delete [-p] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

delete all org shapes for a target org

```
USAGE
  $ sfdx force:org:shape:delete [-p] [-u <string>] [--apiversion <string>] [--json] [--loglevel
    trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

FLAGS
  -p, --noprompt                                                                    do not prompt for confirmation
  -u, --targetusername=<value>                                                      username or alias for the target
                                                                                    org; overrides default target org
  --apiversion=<value>                                                              override the api version used for
                                                                                    api requests made by this command
  --json                                                                            format output as json
  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

DESCRIPTION
  delete all org shapes for a target org

EXAMPLES
  $ sfdx force:org:shape:delete -u me@my.org

  $ sfdx force:org:shape:delete -u MyOrgAlias -p

  $ sfdx force:org:shape:delete -u me@my.org --json

  $ sfdx force:org:shape:delete -u me@my.org -p --json > tmp/MyOrgShapeDelete.json
```

_See code: [src/commands/force/org/shape/delete.ts](https://github.com/salesforcecli/plugin-signups/blob/v1.0.0/src/commands/force/org/shape/delete.ts)_

## `sfdx force:org:shape:list [--verbose] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

list all org shapes you’ve created

```
USAGE
  $ sfdx force:org:shape:list [--verbose] [--json] [--loglevel
    trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

FLAGS
  --json                                                                            format output as json
  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation
  --verbose                                                                         list more information about each org
                                                                                    shape

DESCRIPTION
  list all org shapes you’ve created

EXAMPLES
  $ sfdx force:org:shape:list

  $ sfdx force:org:shape:list --json

  $ sfdx force:org:shape:list --json > tmp/MyOrgShapeList.json
```

_See code: [src/commands/force/org/shape/list.ts](https://github.com/salesforcecli/plugin-signups/blob/v1.0.0/src/commands/force/org/shape/list.ts)_

<!-- commandsstop -->
