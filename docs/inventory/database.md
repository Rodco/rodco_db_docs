# product:

Trigger:

- Id
- created_at
- updated_at
- name [*]
- product_cost_id
- product_brand_id [*]
- product_type_category_id [*]
- unit [*]
- presentation [*]
- code [*]
- product_tax_id [*]
- description [*]
- image_url
- comision_rate [*]
- product_cost_as_price_id
- api_source [*]
- discount_rate

# product_brand:

- id
- name [*]
- api_source [*]

# product_type:

- id
- name [*]
- api_source [*]

# product_type_category:

- id
- name [*]
- product_type_id [*]
- api_source [*]

# packing_list:

- id
- sales_invoce_id [*]
- type [*]
- shipping_supplier_id
- created_at
- prepared_at
- deliveried_at
- shipping_route_id
- received_name
- received_by_signature
- status (draft)
- archived
- api_source [*]
- shipment_cost

# packing_list_item:

- id
- packing_list_id [*]
- product_id [*]
- amount [*]
- api_source [*]

# product_warehouse:

- id
- name [*]
- description [*]
- api_source [*]

# product_warehouse_item:

- id
- product_warehouse_id [*]
- product_id [*]
- inventory [*] {0} (>0)
- api_source [*]

#### product_warehouse_transfer:

- id
- created_at
- applied_at
- status (draft)
- archived
- approved_by_user_id
- created_by_user_id [*]
- reason_for_transfer [*]
- destination_warehouse_id [*]
- source_warehouse_id
- api_source [*]

#### product_warehouse_transfer_item:

- Id
- product_warehouse_transfer_id [*]
- product_id [*]
- amount [* ] { > 0}
- api_source [*]

#### truck:

- id
- name [*]
- license_plate [*]
- brand
- model
- api_source [*]

#### shipping_route:

- Id
- shipped_at
- returned_at
- truck_id [*]
- total_km
- driver_user_id [*]
- assistant_user_id [*]
- status (draft)
- archived
- api_source [*]

#### product_price_list_customer

- id
- product_price_list_id [*]
- customer_id [*]
- created_at
- api_source [*]
