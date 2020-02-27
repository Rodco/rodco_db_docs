# electronic_document_log

Table
document_id [R,F]
type [R,F]
code [R,F]
status [R,F] {printed, registered, validated, notified}

Actions
Retry
Void

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

# Sales Invoice

- table

  - number [R,F]
  - readable_number
  - applied_at [R,F]
  - credit_term [R,F]
  - customer_id [R,F]
  - customer_rep_id [R,F]
  - pdf_url [R,F]
  - currency [R,F]
  - total [R,F]
  - balance [R,F]

Sales invoices should dropdown and display in accordion the list of sales_invoice_items.

Sales_Invoice_Items should have checkboxes or numeric inputs used to insert the amount of items to be returned. Max value of input should be the amount of sales_invoice_items.

- Actions
  - Resend
    - send sales_invoice_id to /sales_invoice/resend
  - Return
    - send sales_invoice_items id's and amounts to /sales_invoice/return

# Order

- Table:
  _ created_at
  _ updated_at
  - applied_at
  - customer_id [R,F,C*]
  - shipping_supplier_id [R,F,C]
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
  - order_items_json
  - tax_exception_json
  - tax_exoneration_json
  - sales_invoce_id
  - quote_id
  - customer_override_type
  - customer_override_identification
  - customer_override_email_for_invoce
  - order_total [R,F]
  - requires_office_approval [R,F]
  - approved_by_office_user_id
  - approved_by_office_at
  - approved_by_office_status [R,F]
  - replaces_sales_invoce_id
  - description [R,F,C*]
  - origin [R,F,C*]

Create

When customer does no exist, there must be the way to quickly create within a Modal. Such created customers only require Name, Province and Phone, Identification, Identification_Type and invoice_email.

- Actions

  - Approve

    - if requires_office_approval
      - must have approved_by_billing_user_id
      - archived=true must have approved_by_office_user_id
    - must have approved_by_billing_user_id
    - must have items in it's JSON
    - set archived=true

  - Duplicate
    - send order id to order/duplicate
