```graphql
type Droid {
  id: String
  name: String
  appearsIn: [Episode]
  primaryFunction: String
}
```

```graphql
enum Episode { NEWHOPE, EMPIRE, JEDI }
```

```graphql

interface Character {
  id: String
  name: String
  friends: [Character]
  appearsIn: [Episode]
}

type Human implements Character {
  id: String
  name: String
  friends: [Character]
  appearsIn: [Episode]
  homePlanet: String
}

type Droid implements Character {
  id: String
  name: String
  friends: [Character]
  appearsIn: [Episode]
  primaryFunction: String
}
```

```graphql
union Error = NotFoundError | AccessError | ValidationError
```

```graphql
scalar DateTime

type Droid {
  id: String
  createdOn: DateTime!
}
```

```graphql
type Query {
  hero(episode: Episode): Character
  human(id: String!): Human
  droid(id: String!): Droid
}
```

```graphql
type Mutation {
  destroyDroid(id: String!): Droid
  destroyHuman(id: String!): Human
}
```

```graphql
type Example {
  oldId: Int!
  @deprecated(
    "reason": "Renamed to use standard naming convention and type for IDs"
    "replacement": "id"
    "deprecatedDate": "2020–10–03T10:45:49–08:00"
    "expirationDate": "2021–01–01T00:00:00–08:00"
  )
}
```

```graphql
type DroidInput {
  name: String!
  appearsIn: [Episode]
}

type Mutation {
  createDroid(input: DroidInput!): DroidResult
}
```

```graphql

type PaginatedList {
  nextPage: String
  previousPage: String
  
}

type Query {
  getItemsByName(name: !String, next: !Int = 10, cursor: String):
}
```
