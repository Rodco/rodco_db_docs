# Overview

# Database

The database is Postgres V.12.2 in production Heroku PostgresDB running behind a connection proxy. Staging and Release DB's are staging versions.

# Server

The server is modeled using Express, the database client is knex, data validation with JSON-Schema and authentication with JWT.

The architecture is based on controllers and services with dependency injection for easy testing.

# Cloud

The server and DB is hosted on the cloud in Heroku. Let roberto@rodcocr.com know if you need access.

The Database and API are based on Postgres, Knex and Express.

# Environments

- Local: localhost:5000
- Staging:
- Production:

# Getting Started

## Install Heroku CLI

- https://devcenter.heroku.com/articles/heroku-cli
- \$ heroku login

## Download Staging DB

- \$ `heroku pg:backups:capture --app hasura-rodco-api-staging`
- \$ `heroku pg:backups:download --app hasura-rodco-api-staging`

## Start postgres with docker and download staging data

- \$ `git clone git@github.com:Rodco/hasura-rodco-api.git`
- \$ `docker-compose up -d`
- \$ `docker exec -i postgres_container_rodco pg_restore --verbose --clean --no-acl --no-owner -U development -d development < latest.dump`

## install, migrate and run

- \$ `npm install .`
- rename .env.example to .env `NODE_ENV=development && DATABASE_URL=postgres://development:development@localhost:5433/development`
- \$ `npm run migrate` -> always run this command after downloading db data
- \$ `npm start`

## Important Points

### Update

When updating an object only send the data that is changing. Current merging strategy is simple {...current, ...incomming}. If a an use case requires a change to this merging strategy it's possible using specific route overrrides.

## Usage

# Routes

Routes are mapped to their respective table under the /api path.

Examples:

- http://localhost:5000/api/customers
- http://localhost:5000/api/products
- http://localhost:5000/api/orders

# Paths

Rest "paths" or "actions" are based on [React-Admin Rest Api](https://marmelab.com/react-admin/DataProviders.html)

## getOne

- method: GET
- route: /{:id}
- returns: {Object}

## getList

- method: POST
- route: /getList
- body: `{ pagination: { page: {int} , perPage: {int} }, sort: { field: {string}, order: {string} }, filter: {Object} }`

- returns: {results: [{Object}], count: {int}}

## getMany

- method: post
- route: /getMany
- body: { ids: {mixed[]} }
- returns: [{Object}]

## getManyReference

- method: post
- path /getManyReference
- body: { target: {string}, id: {mixed}, pagination: { page: {int} , perPage: {int} }, sort: { field: {string}, order: {string} }, filter: {Object} }
- returns: {results: [{Object}], count: {int}}

## update

- method: put
- path: /:id
- body: { data: {Object}}
- returns: {}

## create

- method: post /
- body: { data: {Object}}

## updateMany

- method: post /updateMany
- body: { data: {Object}, ids: [mixed[]]}
- returns: {}

## delete

- method: delete
- path: /:id
- returns: {}

## deleteMany

Not Implemented

## custom actions

- method: post
- route /actions/{:action}
- body: {metadata: {Object}, id: {int}}
- returns: {Object}

## custom bulk actions

- method: post
- route /bulk/{:action}
- body: { metadata: {Object}, ids: [mixed[]]}
- returns: [{Object}]

## Headers

Every request, except for login requests. Require an Autorization Header.

- Accept: "application/json"
- Authorization: `Bearer ${token}`

```

```
