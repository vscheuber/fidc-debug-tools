# fidc-debug-tools
ForgeRock Identity Cloud Debug Tools

## Overview
The Identity Cloud Debug Tools are a set of node.js-based shell scripts that allow tailing of log files to debug custom configurations and scripts.

The tools break down into two main components:
- tail.js - The backend library that handles log record retrieval and provides default log output capabilities as well. This library is referenced by the other scripts.
- tail_xyz.sh - Specialized scripts to debug specific cloud components. These scripts potentially overwrite the default log output capabilities of tail.js and they provide filter configurations to limit the output to relevant data for the task.

## Install dependencies:
The scripts require `dotenv` to externalize envirment configuration. install it via `npm`:
```
$ npm install dotenv --save
```

## Configure a `.env` file for your cloud tenant
Modify the sample `.env` file provided in this repository to match your environment:
```
# Specify the full base URL of the FIDC service.
ORIGIN=https://openam-volker-dev.forgeblocks.com

# Specify the log API key and secret,
# as described in https://backstage.forgerock.com/docs/idcloud/latest/paas/tenant/audit-logs.html#api-key
API_KEY_ID=2b8b8bba423680305e678be18e80c8be
API_KEY_SECRET=cfb8ec126de8bdd829b0386a5dbf9f0eb6fe7b8a16ba9c560b7f65949e607985
```

## Review default filter settings in the tail_* scripts
