# Large System Development, Fall 2020

## **Team B**

## Project CI status

![Frontend CI](https://github.com/TEAM-B-SOFT2020/LSDFrontEnd/workflows/FRONTEND%20CI/badge.svg) ![Backend CI](https://github.com/TEAM-B-SOFT2020/LSDBackEnd/workflows/Backend%20CI/badge.svg)

[Case 2](https://datsoftlyngby.github.io/soft2020fall/resources/aa00a079-case-2.pdf)

## Assignments

1. [Logical Data Model](assignments/logical-data-model.md)
2. [Use Case Model](assignments/use-case-model.md)
3. [System Operations Contract](assignments/system-operations-contract.md)

## Contract

[Contract repository](https://github.com/TEAM-B-SOFT2020/LSDContract)

## Backend Application

[Backend repository](https://github.com/TEAM-B-SOFT2020/LSDBackEnd)

### Setup

#### Installation

```bash
npm install
```

#### MongoDB

1. Log in to your mongodb account on [atlas](https://account.mongodb.com/account/login)
2. Create a database named something like **lsdbackend** or whatever you prefer.
3. Create a `.env` file in the root of the project and insert your connection string like this:

```bash
CONNECTION_STRING=your production connection string with credentials
TEST_CONNECTION_STRING=your development connection string with credentials
# Remember not to use space separation
# - and that the connection strings cannot be identical.
```

4. Populate the production database by running:

```bash
npm run populate
```

### Test

```bash
npm run test
```

### Execute the application

The application uses Remote Procedure Call (RPC) to connect with the frontend application.  
It listens on `localhost:3000`  
When the application is running the monitor is reachable on `localhost:3000/status`
Logs is located at `logs/error.log` and `logs/info.log` in the root folder.

```bash
npm run start
```

### Service Level Agreement and Brancing Strategy

The Service Level Agreement can be found [here](https://github.com/TEAM-B-SOFT2020/LSDBackEnd/wiki/Service-Level-Agreement)  
A figure of our brancing strategy can be found [here](https://github.com/TEAM-B-SOFT2020/LSDBackEnd/wiki)
....


## Frontend Application

[FrontEnd repository](https://github.com/TEAM-B-SOFT2020/LSDFrontEnd)

### Setup

1. Download the repository.
2. In the root of the project, make a ```bash .env``` file.
3. Insert into the .env file:

```bash
NODE_ENV=development
RPC_HOST=http://localhost:3000/
PORT=4000
```
4. In terminal 



```bash
yarn install
```

5. In terminal

```bash
yarn add TEAM-B-SOFT2020/LSDContract
```

### Tests

```bash
yarn test
```

### Execute the application

Run application

If you have docker installed, you can run everything using the following command:

```bash
yarn monitor (Takes a few seconds)
```
The prometheus.yml file is configured to install a docker image of the application and run grafana service.


You can now open the application on port :4000
```bash
http://localhost:4000 - for application 
```

```bash
http://localhost:4000/api - for API
```


Alternatively you can run the application without monitoring:
```bash
yarn dev
```


### Logging and Monitoring.
When the application is running. We log both errors and information about data retrival and input.
In the logger.ts file we specify two text files to store logs. The text files are saved in './logs/errors.log' and './logs/info.logs'
The loggers are defined by levels 'level: 'error'' for erros and 'level: 'info'' for general info.


If you ran the application using the docker image, you have access to the prometheus monitor Dashboard.

```bash 
http://localhost:3000 - for grafana 
```
1. You will be presented with a login screen - create a user, and login.
2. Then navigate to Configuration (cogwheel) > Data Sources > Add Data Source (Big green button). 
3. In 'Settings':
4. Set URL to 'http://localhost:9090'
5. Set Access to 'Browser'
6. Next to 'Settings' click 'Dashboards' and select 'Prometheus 2.0 Stats'
7. Navigate to the 'Dashboard'(four squares) in the left navigation bar > Manage > Select 'Prometheus 2.0 Stats'
8. Now bask in its glory. 

....
