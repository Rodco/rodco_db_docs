# product:
Id
created_at
updated_at
name
product_cost_id
product_brand_id
product_type_category_id
unit
presentation
code
product_tax_id
description
image_url
comision_rate
short_code


# product_brand:
id
name
# product_type:
id
name
 
# packing_list:
id
sales_invoce_id
type
created_at
prepared_at
deliveried_at
shipping_route_id
received_name
received_by_signature
status
archived

# packing_list_item:
id
packing_list_id
product_id
amount

 
# truck:
id
name
license_plate
brand
model

# shipping_route:
Id
shipped_at
returned_at
truck_id
total_km
driver_user_id
assistant_user_id
status
archived 