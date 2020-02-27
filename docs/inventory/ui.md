# product:

- Table

  - id
  - name [R,F,C*]
  - product_brand_id [R,F,C*]
  - product_type_category_id [R,F,C*]
  - unit [R,F,C*]
  - presentation [R,F,C*]
  - product_tax_id [R,F,C*]
  - description [R,F,C*]
  - image_url

  Dropdown collapse with inventory details
  Note: Will try to create view that show total calculated inventory

  There must be a way to batch edit a single field of several products at once. [discount]

  - actions
    - create
    - deactivate
      - set active=false

# product_brand:

- Table

  - id
  - name [R,F,C*]

- actions
  - create

# product_type:

- Table

  - id
  - name [R,F,C*]

- actions
  - create

# product_type_category:

- Table

  - id
  - name [R,F,C*]
  - product_type_id [R,F,C*]

- actions
  - create

# packing_list:

Table

- id
- sales_invoce_id [R,F]
- type [R,F,U]
- shipping_supplier_id [R,F,U]
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

# product_warehouse:

Table

- name [R,F,C*]
- description [R,F,C*]

  Table should include accordion drop down with

- Actions
  - create

# product_warehouse_item:

Table

- product_warehouse_id [R,F]
- product_id [R,F]
- inventory [R,F]

Filterable by product_warehouse_id and product's [product_brand_id, product_type_category_id, product_type_id]

# product_warehouse_transfer:

Table

- created_at
- applied_at
- status (draft)
- approved_by_user_id [R,F]
- created_by_user_id [R,F]
- reason_for_transfer [R,F,C*]
- destination_warehouse_id [R,F,C*]
- source_warehouse_id [R,F]

  Should display dropdown accordion with product_warehouse_transfer_item under each transfer

- Actions
  - Create
  - Approve
    Sets archived=true and approved_by_user_id

# truck:

- table

  - id
  - name [R,F,C*]
  - license_plate [R,F,C*]
  - brand [R,F,C*]
  - model [R,F,C*]

- actions
  - create

# shipping_route:

- table

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

# supplier_invoice:

Table
id
created_at
updated_at
supplier_id [R,F]
applied_at
received_at [R,F,U]
ordered_at [R,F,U]
purchase_order_id [R,F]
status (draft)
product_warehouse_id [R,F,U]
archived
currency [R,F] {\$,EU,C/}
total [R,F]
total_pending_payment [R,F]
payment_status [R,F]

dropdown with accordion to show supplier_invoice_item's and supplier_invoice_item_received

Actions
Receive
