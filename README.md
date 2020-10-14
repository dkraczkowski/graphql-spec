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
type Query {
  hero(episode: Episode): Character
  human(id: String!): Human
  droid(id: String!): Droid
}
```

```graphql
union Error = NotFoundError | AccessError | ValidationError
```

```graphql
type Mutation {
  destroyDroid(id: String!): Droid
  destroyHuman(id: String!): Human
  
}
```

