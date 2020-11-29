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

## Frontend Application

....
