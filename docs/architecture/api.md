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
- Staging: hasura-rodco-api-staging.herokuapp.com
- Production: hasura-rodco-api-production.herokuapp.com

## Important Points

### Update

When updating an object only send the data that is changing. Current merging strategy is simple {...current, ...incomming}. If a an use case requires a change to this merging strategy it's possible using specific route overrrides.

### Complex Filters

For Filters that do not use the equal `COL=VALUE` operation, we added a simple deviation from the standard that appends `,` + `OPERATION_NAME` to the column being filtered. To use this feature simple add the suffix of `comma` + the PGSQL operation.

For example for filtering by an array of values use: `{"status,IN" :[ {String},{String},{String} ] }`

If the value is an array, by default we use the IN Operand: `{"status" :[ {String},{String},{String} ] }`

For example for filtering > use: `{"total,>" : 100 }`

For example for filtering >= use: `{"total,>=" : 100 }`

For range use the between operand >= use: `{"total,between=" : [100,1000] }`

To use the pg LIKE or ILIKE operation there are two options:

If the value of any string filter contains a `%`, then the operation is switched to ilike. Otherwise use the operation as usual for example: {"name,ilike": "rob"}. This will filter name using ilike and automatically wrap the string rob like this `%rob%`.

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
- route /action/{:action}
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
