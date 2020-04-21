# product:

### User Stories:

- Logistic Reps create new products and edit product modifications for maintenance.
- Logistic Reps and regular users need to see the inventory total and on each warehouse by opening a dropdown row.
- Logistic Reps need to assign multiple products to one product_type_category_id and one product_brand_id

* Table

  - id
  - name [R,F,C*]
  - product_brand_id [R,F,C*]
  - product_type_category_id [R,F,C*]
  - unit [R,F,C*]
  - presentation [R,F,C*]
  - description [R,F,C*]
  - inventory [R]
  - image_url

  There must be a way to batch edit a single field of several products at once. [discount]

  - actions
    - create
    - deactivate
      - set active=false

# product_brand:

### User Stories:

- Logistic Reps need to create product brands

* Table

  - id
  - name [R,F,C*]

* actions
  - create

# product_type:

- Logistic Reps need to create product types

* Table

  - id
  - name [R,F,C*]

* actions
  - create

 
# packing_list:

# User Stories

- packing_list are created automatically after a Sales Invoice is created.
- Logistic Rep like to see the products of the packing_list, by opening a popup or dropdown row.
- Logistic Reps would like to print packling_lists for packing & labeling
- Logistic Reps would like to add packing_list to current shipping_routes
- Logistic Reps would like to mark packing_list as prepared by using a button
- Logistic Reps would like to set the shipment_cost of a packing_list sent via supping providers.
- Logistic Reps would like to mark the packing_list as delivered for in store pickup.

Table

- id
- sales_invoce_id [R,F]
- type [R,F,U]
- created_at
- prepared_at
- deliveried_at [R,F,U]
- shipping_route_id [R,F,U]
- status [R,F,U]
- shipment_cost [R,F,U]

  Should display dropdown accordion with packing_list_item under each packing_list

- Actions
  - Receive
    - Show pop up with canvas to get signature from customer
  - Print
    Print selected packing list and items
  - Add to Shipping Route
    popup to select from active shipping routes
    update field shipping_route
    set status=shipped
  - deliver
    set deliveried_at
    set archived=true
 
# truck:

- Logistic Reps need to create truck

* table

  - id
  - name [R,F,C*]
  - license_plate [R,F,C*]
  - brand [R,F,C*]
  - model [R,F,C*]

* actions
  - create

# shipping_route:

- Logistic Reps need to create shipping_route's for each truck departure

* table

  - id
  - shipped_at [R,F,C]
  - returned_at [R,F,C]
  - truck_id [R,F,C*]
  - total_km [R,F,C*]
  - driver_user_id [R,F,C*]
  - assistant_user_id [R,F,C*]
  - status [R,F,C*]

  - Actions
    - Create
    - Complete
