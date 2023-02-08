# bankapp-mock-api

#### Prerequisite
* Create a folder
```
mkdir bankapp-mock-api
cd bankapp-mock-api
```

#### Step 1: Create a node js project
```
npm init -y
```

#### Step 2: Install json server dependency
```
npm i json-server
```

#### Step 3: Create server.js
```js
const jsonServer = require('json-server')

const server = jsonServer.create()

const router = jsonServer.router('db.json')
const middlewares = jsonServer.defaults()
 
server.use(middlewares)
server.use('/api', router)
server.listen(process.env.PORT || 5000, () => {
  console.log('JSON Server is running')
})


```


#### Step 4: Create db.json
```js
{
    "users": [
        { "id": 1, "name":"Amit Kumar Saini", "email":"iamaksaini68@live.com", 
        "password":"pass123", "role": "USER"
        },
        { "id": 2, "name":"Virat Saini", "email":"viratsaini68@gmail.com", 
            "password":"pass123", "role": "ADMIN"
        }
    ],
    "accounts":[

    ],
    "transactions":[

    ]
}
```

#### Step 5: Run the Node JS Project
```
node server.js
```

#### Step 6: Test - List Users API 
```
http://localhost:9090/api/users
```

Output:
```js
[
 {
 id: 1,
 name: "Amit Kumar Saini",
 email: "imaksaini68@live.com",
 password: "pass123",
 role: "USER"
 },
{
 id: 2,
 name: "Virat Saini",
 email: "viratsaini68@gmail.com",
 password: "pass123",
 role: "ADMIN"
}
]
```

#### Step 7: Test - View User Details API 
```
http://localhost:9090/api/users/1
```

Output:
```js
 {
 id: 1,
 name: "Amit Kumar Saini",
 email: "imaksaini68@live.com",
 password: "pass123",
 role: "USER"
 }
```
