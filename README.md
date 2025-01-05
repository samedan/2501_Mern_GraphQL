### This Git

> https://github.com/samedan/2501_Mern_GraphQL.git

## Helping commands

> https://gist.github.com/bradtraversy/fc527bc9a4659ab8de8e8066f3498723

### GraphQL Schema Working

> http://localhost:5000/graphql
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

### Scheman Mongoose

> /server/models/Client.js,Project.js

# Project.js belongs to Client

```
clientId: {
    type: mongoose.Schema.Types.ObjectId,
    ref: "Client",
  },
```

### Queries (read) & Mutations (write)

```
mutation{
  addProject(name: "Mobile App", description: "desc", status: new, clientId: "677ad19f49e6e6d0e41abd90") {
    name
    id
  }
}
```
