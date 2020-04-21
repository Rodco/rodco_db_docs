### Rodco S.A.

Welcome to the Documentation for Rodco S.A. Administrative System.

The system consists of Progressive Web App based on REACT-ADMIN with a NODEJS Api backend.

#### Enviromnments

We have 3 environments
##### UI
* In AWS S3 with Cloudfront
- development: localhost:3000
- staging: http://admin-staging.rodcocr.com/
- production: http://admin.rodcocr.com/

Setup: NPM Install
Run with staging: npm start
Run with local API: npm run dev

##### API
In Heroku
- development: localhost:4000
- staging: https://hasura-rodco-api-staging.herokuapp.com/
- production: https://hasura-rodco-api-production.herokuapp.com/

Setup: Npm Install

Tests:
mocha ./test/integration

##### DB
Postgres in Heroku
- development: localhost
- staging: dbs.rodcocr.com
- production: dbp.rodcocr.com

Setup in API REPO:
- CREATE_DATABASE test1
- npm run migrate



