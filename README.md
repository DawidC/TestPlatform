# TestPlatform

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
cd opentestplatform-backend && npm run classic
```

Frontend only:
```
cd opentestplatform-client && npm start
```

Backend structure:
src
│   app.js          # App entry point
└───api             # Express route controllers for all the endpoints of the app
└───config          # Environment variables and configuration related stuff
└───jobs            # Jobs definitions for agenda.js
└───loaders         # Split the startup process into modules
└───models          # Database models
└───services        # All the business logic is here
└───subscribers     # Event handlers for async task
└───types           # Type declaration files (d.ts) for Typescript