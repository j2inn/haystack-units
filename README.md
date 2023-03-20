<p align="center">
  <a href="https://github.com/j2inn/haystack-units/actions/workflows/master-push.yaml">
    <img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/j2inn/haystack-units/master-push.yaml" />
  </a>

  <a href="https://github.com/j2inn/haystack-units/blob/master/LICENSE">
    <img alt="GitHub" src="https://img.shields.io/github/license/j2inn/haystack-units" />
  </a>
</p>

# Haystack Unit Database

The unit database for [haystack-core](https://github.com/j2inn/haystack-core).

This project compiles a complete unit database that can be used an application to convert between different numerical units.

Since there are a lot of units (that an application may or may not use), the database is built into this separate library instead of [haystack-core](https://github.com/j2inn/haystack-core).

The database is compiled from Fantom's unit database file [units](https://github.com/fantom-lang/fantom/blob/master/etc/sys/units.txt) which in turn is based on the unit database from [oBIX](http://www.obix.org/).

When this module is built, the units database is parsed and compiled into [TypeScript](https://www.typescriptlang.org/). Therefore every unit has its strongly typed with its own name.

In order for units to be successfully used with HNum either the whole unit database just the units the user is interested in must be imported.

## Installation

```
npm install haystack-core haystack-units
```

## APIs

Please click [here](http://j2-docs.s3-website-us-east-1.amazonaws.com/j2inn/haystack-units/index.html) for the API documentation.

## Importing

To import the whole unit database into your application...

```typescript
import 'haystack-units'
```

...or...

```typescript
import units from 'haystack-units'
```

If you're developing an UI application that uses webpack, you may want to only import the particular units you're interested in. This will employ tree shaking to ensure only the units your application is using is built into your app...

```typescript
import {second, millisecond} from 'haystack-units'

...
const msNum = secondsNum.convertTo(millisecond)
```

When using this approach remember to import the units you are intending to convert to (millisecond) and from (second).

Please see [HNum](https://github.com/j2inn/haystack-core/blob/master/src/core/HNum.ts) and [HUnit](https://github.com/j2inn/haystack-core/blob/master/src/core/HUnit.ts) in [haystack-core](https://github.com/j2inn/haystack-core) for more information.
