# product:

- Table

  - name
  - product_brand_id
  - product_type_category_id
  - unit
  - presentation
  - product_tax_id
  - description
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
  - name

- actions
  - create

# product_type:

- Table

  - id
  - name

- actions
  - create

# product_type_category:

- Table

  - id
  - name
  - product_type_id

- actions
  - create

# packing_list:

Table

- sales_invoce_id
- type
- shipping_supplier_id
- created_at
- prepared_at
- deliveried_at
- shipping_route_id
- status
- shipment_cost

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

# packing_list_item:

Table

- id
- packing_list_id
- product_id
- amount

# product_warehouse:

Table

- name
- description
- items_json

  Table should include accordion drop down with

- Actions
  - create

# product_warehouse_item:

Table

- product_warehouse_id
- product_id
- inventory

Filterable by product_warehouse_id and product's [product_brand_id, product_type_category_id, product_type_id]

# product_warehouse_transfer:

Table

- created_at
- applied_at
- status
- approved_by_user_id
- created_by_user_id
- reason_for_transfer
- destination_warehouse_id
- source_warehouse_id

  Should display dropdown accordion with product_warehouse_transfer_item under each transfer

- Actions
  - Create
  - Approve
    Sets archived=true and approved_by_user_id

# product_warehouse_transfer_item:

- Table

  - product_warehouse_transfer_id
  - product_id
  - amount

# truck:

- table

  - name
  - license_plate
  - brand
  - model

- actions
  - create

# shipping_route:

- table

  - shipped_at
  - returned_at
  - truck_id
  - total_km
  - driver_user_id
  - assistant_user_id
  - status

  - Actions
    - Create
    - Complete

# supplier_invoice:

Table
created_at
updated_at
supplier_id
applied_at
received_at
ordered_at
purchase_order_id
status
product_warehouse_id
archived
currency
total
total_pending_payment
payment_status

dropdown with accordion to show supplier_invoice_item's and supplier_invoice_item_received

Actions
Receive
