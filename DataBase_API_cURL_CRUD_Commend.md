## Making request to manager node database

# CRUD operation cURL commend 

*commend must be one line.

### Create

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"mutation{createUser(options:{firstName: \"abc\",lastName: \"def\",age:50}){id,firstName,lastName,age}}"}' http://10.176.67.91:4000/graphql
```

### Read

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"getUser{id,firstName,lastName,age}"}' http://10.176.67.91:4000/graphql
```

### Update

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"updateUser(id:2,input:{firstName:\"Conrad\",lastName:null,age:null})"}' http://10.176.67.91:4000/graphql
```

### Delete

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"mutation{deleteUser(id:2)}"}' http://10.176.67.91:4000/graphql
```
