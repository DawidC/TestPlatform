# TestPlatform

Requirements:
1. node >= v12.13.1
2. npm  >= 6.12.1
3. in opentestplatform-backend => mv config.json.example -> config.json and change mongodb connection string to local connection string, or to mongodb atlas connection string (required free accound with free tier cluster (https://www.mongodb.com/cloud/atlas))

To run app (backend + frontend)
```
npm start
```

Backend only:
```
cd opentestplatform-backend && node server.js
```

Frontend only:
```
cd opentestplatform-client && npm start
```

