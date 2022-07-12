# Awesome Links - part-1

This branch has the same starting point as [this article](https://prisma.io/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw)

## All steps

1. setup and rename .env

2. setting up prisma in our project

- npm i -D prisma
- npx prisma init
- create prisma schema
- setting up a PostgreSQL database
- npx prisma db push (set the databse sychronously without need to generate migration history)

- setting up prisma in our project

- seeding the database using Prisma

- npm i ts-node -D
- npx prisma db seed --preview-feature
- npx prisma studio

3. making GraphQL API using Apollo Server 3 and Prisma

- npm i apollo-server-micro graphql micro-cors

- graphql/schema.ts ~ define schema of the app

- /pages/api/graphql.ts ~ Creating the GraphQL endpoint

4. connecting graphQL api with prisma database

- /lib/prisma.ts ~ initialize prisma client

- /graphql/context.ts ~ Creating a GraphQL context

- update the /pages/api/graphql.ts file to include the context

- Inside the /graphql/resolvers.ts file, update the `links function to the following code
  Before it was containing a json object and now it is fetching data from prisma database

- The flaws with our current GraphQL setup

- Resolvers must match the same structure as the schema and vice-versa. Otherwise, you can end up with buggy and unpredictable behavior. These two components can accidentally go out of sync when the schema evolves or the resolver implementation changes.

- The GraphQL schema is defined as strings, so no auto-completion and build-time error checks for the SDL code.

---

Nexus is a GraphQL schema construction library where you define your GraphQL schema using code. The value proposition of this approach is you are using a programming language to build your API, which has multiple benefits:

- No need to context-switch between SDL and the programming language you are using to build your business logic.
- Auto-completion from the text-editor
- Type-safety (if you are using TypeScript)

5. Building a GraphQL schema using Nexus, Prisma and Nextjs

- install nexus ~ npm install nexus

- in the /graphql/schema.ts file replace the typeDefs

- update the import in the /pages/api/graphql.ts file

- in the browser graphQL playground we get ok: true
