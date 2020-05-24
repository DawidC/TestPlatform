# TestPlatform
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)


Requirements:
1. node >= v12.13.1
2. npm  >= 6.12.1
3. in opentestplatform-backend => mv src/config/config.json.example -> /src/config/config.json and change mongodb connection string to local connection string, or to mongodb atlas connection string (required free accound with free tier cluster (https://www.mongodb.com/cloud/atlas))

To run app (backend + frontend)
```
npm start
```

Backend only:
```
npm i -g tsc ts-node ts-mocha tslint nodemon
npm i -D
cd opentestplatform-backend && npm run build 
```

Frontend only:
```
cd opentestplatform-client && npm start
```

Backend structure:
```
├── src
│   ├── apiV1
│   │   ├── controllers
│   │   │  ├── authController.ts
│   │   │  └── userController.ts
│   │   ├── models
│   │   │   ├── userModel.ts
|   |   ├── routes
│   │   │   ├── authRoute.ts
|   |   |   └── userRoute.ts
│   │   └── index.ts
│   ├── config
│   │   ├── config.ts
│   │   └── db.ts
│   ├── helpers
│   │   ├── errorHandler.ts
│   │   └── verifyToken.ts
│   ├── .env.example
│   ├── App.ts
│   └── index.ts
├── .editorconfig
├── .gitignore
├── package.json
├── README.md
├── tsconfig.json
└── tslint.json

test
#TBD
```

### Installation

1. install the dependencies using `npm install` or `npm i`

2. Rename the file `.env.example` to `.env`, then you need to configure the file `config.ts` located in `src/config`

3. Start the app using `npm run dev`

4. After that, go to: `http://localhost:3000/v1/users`


### Available routes

| Method   | Resource        | Description                                                                                                                                 |
| :------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `POST`   | `/register`     | Create a new user in the DB. You need to specify in the body the following attributes: name, lastname, email & password.                    |
| `POST`   | `/authenticate` | Sign in with the email & password. If it's successful, then generates a token                                                               |
| `GET`    | `/users`        | Returns the collection of users present in the DB.                                                                                          |
| `GET`    | `/users/:id`    | It returns the specified id user. You need to specify the token in the header with the following format: `Authorization: Bearer your-token` |
| `PUT`    | `/users/:id`    | Updates an already created user in the DB                                                                                                   |
| `DELETE` | `/users/:id`    | Deletes a user from the DB                                                                                                                  |

### Available scripts

- `build` - Transpile TypeScript to ES6,
- `lint` - Lint your TS code,
- `dev` - To run the app without transpile to ES6,
- `clean` - Remove dist, node_modules, coverage folders,
- `start` - Run the transpiled app
- `prod` - Build & run the transpiled app
