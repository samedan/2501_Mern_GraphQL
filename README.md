### This Git

> https://github.com/samedan/2501_Mern_GraphQL.git

### GraphQL Schema Working

> ![GraphQL](https://github.com/samedan/2501_Mern_GraphQL/blob/main/public/printscreens/01printscreen.jpg)

## Schema

> /server/schema.js -> const RootQuery()

### Get CLient with Project

> schema.js

```
const ProjectType = new GraphQLObjectType({
  name: "Project",
  fields: () => ({ ...
    client: {
      type: ClientType,
      resolve(parent, args) {
        return clients.find((client) => client.id === parent.clientId);
      },
    },
  }),
});
```
