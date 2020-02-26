#### Database

The Database and API are based on Hasura.io which are hosted on Heroku.

The API follow Hasura GraphQl Standard and should be connected to React-Admin using https://github.com/Steams/ra-data-hasura-graphql

All database actions are pure, meaning that they directly modify data. We use Hasura Event's system to trigger serverless functions on specific scenarios. Typically this involves setting archived=true and api_source=UI. There are some cases where we'll trigger events on create as well.

Delete and update operations are allowed from Hasura if archived=true, if there is no archived field on the table then they are not allowed.

#### Business Layer

The Business Layer is based on serverless functions that respond to hasura events asyncrounsly. A function can modify the database directly for one or more tables. Such updates or creates must set the record api_source=LAMBDA. In case of error, an async_notification row must be created with data from the original row that triggered the event.
