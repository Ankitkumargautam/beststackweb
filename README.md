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
