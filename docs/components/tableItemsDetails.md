### Table Item Details

- Areas used:
  - Tables that have one-to-many relationships with a items table

#### Overview

The way we work around creating items is we create every object in draft mode, and the items ( for example order items ) are stored in a field called items_json. When the order is approved ( archived=true ) then the backend system takes care of transforming it into the child items.

#### Context

This component is used in tables that have a dropdown accordion.

#### Details

If the parent object is archived=true then load and display the related items from the database. If the parent object is archived=false then display the items from the field items_json
