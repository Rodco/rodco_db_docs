# product:

Trigger:

- Id
- created_at
- updated_at
- name [*]
- product_cost_id
- product_brand_id [*]
- product_type_id [*]
- unit [*]
- presentation [*]
- code [*]
- description [*]
- image_url
- comision_rate [*]
- price
- cost
- inventory

- discount_rate
- short_code

# product_brand:

- id
- name [*]


# product_type:

- id
- name [*]

 


# packing_list:

- id
- sales_invoce_id [*]
- type [*]
- created_at
- prepared_at
- deliveried_at
- shipping_route_id
- received_name
- received_by_signature
- status (draft)
- archived

- shipment_cost

# packing_list_item:

- id
- packing_list_id [*]
- product_id [*]
- amount [*]

  

#### truck:

- id
- name [*]
- license_plate [*]
- brand
- model


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


#### product_price_list_customer

- id
- product_price_list_id [*]
- customer_id [*]
- created_at


#### product_purchase:
- id
- created_at
- updated_at
- status
- applied_at
- archived
- approved_by_user_id
- created_by_user_id
- reference
- items_json
  