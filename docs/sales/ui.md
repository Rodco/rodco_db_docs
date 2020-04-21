
# product_price_list:

Table
name [R,F,C*]
markup [R,F,C*]
number_of_custom_prices [ from view? or trigger if not possible ]

- Actions
  - create

# product_price_list_item:

Table
product_id [name, brand, category, type][r,f,c*]
markup [R,F,C*]
product_price_list_id [R,F,C*]

- Actions
  - Delete
  - Create
  - Update Bulk
    - Optional [Should show a modal to set the markup and discount for all selected prices]

# quote:

Table
created_at
updated_at
applied_at
customer_id [R,F,C*]
status
customer_rep_id
customer_order_number [R,F,C]
credit_term [R,F,C*]
currency [R,F,C*]
shipping_date [R,F,C*]
items_json
total [R,F]
requires_office_approval [R,F]
description [R,F,C]

Actions
Archive
Turn into Order

# Order

- Table:
  _ created_at
  _ updated_at
  - applied_at
  - customer_id [R,F,C*]
  - status [R,F]
  - customer_rep_id [R,F]
  - customer_order_number [R,F,C]
  - approved_by_billing_user_id
  - approved_by_billing_at
  - approved_by_billing_status [R,F]
  - credit_term [R,F]
  - currency [R,F,C*]
  - exchange_rate [R,F,C*]
  - shipping_date [R,F,C]
  - items_json
  - tax_exception_json
  - tax_exoneration_json
  - sales_invoce_id
  - quote_id
  - total [R,F]
  - requires_office_approval [R,F]
  - approved_by_office_user_id
  - approved_by_office_at
  - approved_by_office_status [R,F]
  - replaces_sales_invoce_id
  - description [R,F,C*]
  - origin [R,F,C*]
  - transport_id [R,F,C*]


Create

When customer does no exist, there must be the way to quickly create in the same view. Such created customers only require Name, Province and Phone, Identification and email_for_invoice.

- Actions
  - Apply - Everybody
  - Approve - Billing Executives
  - Hold  - Billing Executives
  - Route - Sales Executives
  - Print - Sales Executives
  - Duplicate - Sales Executives
    - send order id to order/duplicate




