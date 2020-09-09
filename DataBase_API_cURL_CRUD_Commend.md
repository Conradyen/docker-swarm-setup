## Making request to manager node database

# CRUD operation cURL commend 

* NOTE:commend must be in one line.

### Create

Insert user to database.

Required field:

firstName: String
lastName: String
age: Integer

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"mutation{createUser(options:{firstName: \"abc\",lastName: \"def\",age:50}){id,firstName,lastName,age}}"}' http://10.176.67.91:4000/graphql
```

### Read

Get all users in the database.

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"query{getUser{id,firstName,lastName,age}}"}' http://10.176.67.91:4000/graphql
```

### Update

Update user data in data base.

Required field:

id : Integer
input: JSON

```
input type : {
firstName:String,
lastName:String,
age:Integer // can be null
}
```

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"mutation{updateUser(id:2,input:{firstName:\"Conrad\",lastName:\"bob\",age:null})}"}' http://10.176.67.91:4000/graphql
```

### Delete

Delete a user.

Required field:

id : Integer

```
curl -X POST -H "Content-Type: application/json" -d '{"query":"mutation{deleteUser(id:2)}"}' http://10.176.67.91:4000/graphql
```
