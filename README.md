# Egghead Go GraphQL

# Installing

You'll need golang installed. I built the example with 1.12.4.

```
brew install go
```

# Running

Since the project uses go mod, the dependencies will install when first run. 

```
go run server/server.go
```

# Running Queries

After the server is up and running, go to http://localhost:8080 to get a GraphQL
playground that you can run queries in.

# Creating Todos

To execute a GraphQL mutation, run the following query with any text and user
id. The user id is later used to construct a user name as if we were getting the
user from a database.

```graphql
mutation createTodo {
  createTodo(input: {text: "get something", userId: "1"}) {
    user {
      id
    }
    text
    done
  }
}
```

# Fetching Todos

Run the following query to fetch todos that have been created.

```graphql
query findTodos {
  todos {
    text
    done
    user {
      name
    }
  }
}
```
