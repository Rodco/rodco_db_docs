Full javascript, no type-script
Maintainable code - following a defined pattern/architecture that we agree upon

Important Features
Graphql subscriptions to update list on backend changes
No object with archived=true can be updated or deleted
Easily adjustable layouts, forms, tables, filters, actions ( react-admin Docs patterns )
I18n


Every create and update must set the field api_source=UI. Create is optional, but update is required. If this is a problem we must figure out how to do it in triggers.