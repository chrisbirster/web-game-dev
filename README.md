[![CI](https://github.com/perkinsjr/t3-turbo-and-clerk/actions/workflows/ci.yml/badge.svg)](https://github.com/perkinsjr/t3-turbo-and-clerk/actions/workflows/ci.yml)

# Web Game Dev 

## Code Layout

```
.github
  └─ workflows
        └─ CI with pnpm cache setup
.vscode
  └─ Recommended extensions and settings for VSCode users
apps
  └─ next.js
      ├─ Next.js 13
      ├─ React 18
      └─ E2E Typesafe API Server & Client
packages
 ├─ api
 |   └─ tRPC v10 router definition
 └─ db
     └─ typesafe db-calls using Prisma
```

## Quick Start

To get it running, follow the steps below:

### Setup dependencies

```diff
# Install dependencies
pnpm i


# Configure environment variables.
# There is an `.env.example` in the root directory you can use for reference
cp .env.example .env

# Push the Prisma schema to your database
pnpm db-push
```

## Deployment

### Next.js

#### Prerequisites

_We do not recommend deploying a SQLite database on serverless environments since the data wouldn't be persisted. I provisioned a quick Postgresql database on [Railway](https://railway.app), but you can of course use any other database provider. Make sure the prisma schema is updated to use the correct database._

#### Deploy to Netlify

Let's deploy the Next.js application to Netlify. You can use the [Netlify CLI](https://docs.netlify.com/cli/get-started/) to deploy the application.

```diff
# Install the Netlify CLI
npm install netlify-cli -g

# Login to your Netlify account
netlify login

# Deploy the Next.js application
netlify deploy
```

## References

The stack originates from [create-t3-turbo](https://github.com/t3-oss/create-t3-turbo).
