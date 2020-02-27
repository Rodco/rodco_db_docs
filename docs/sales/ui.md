# electronic_document_log

Table
document_id
type
code
status

Actions
Retry
Void

# product_price_list:

Table
name
markup
discount
number_of_custom_prices [ from view? or trigger if not possible ]

- Actions
  - create

# product_price_list_item:

Table
product_id [name, brand, category, type]
markup
product_price_list_id
discount

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
customer_id
status
customer_rep_id
customer_order_number
credit_term
currency
shipping_date
quote_items_json
order_total
requires_office_approval
description

Actions
Archive
Turn into Order

# Sales Invoice

- table

  - number
  - applied_at
  - credit_term
  - customer_id
  - customer_rep_id
  - pdf_url
  - currency
  - total
  - balance

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
  - customer_id
  - shipping_supplier_id
  - status
  - customer_rep_id
  - customer_order_number
  - approved_by_billing_user_id
  - approved_by_billing_at
  - approved_by_billing_status
  - credit_term
  - currency
  - exchange_rate
  - shipping_date
  - order_items_json
  - tax_exception_json
  - tax_exoneration_json
  - sales_invoce_id
  - quote_id
  - customer_override_type
  - customer_override_identification
  - customer_override_email_for_invoce
  - order_total
  - requires_office_approval
  - approved_by_office_user_id
  - approved_by_office_at
  - approved_by_office_status
  - replaces_sales_invoce_id
  - description
  - origin

* Actions

  - Approve

    - if requires_office_approval
      - must have approved_by_billing_user_id
      - archived=true must have approved_by_office_user_id
    - must have approved_by_billing_user_id
    - must have items in it's JSON
    - set archived=true

  - Duplicate
    - send order id to order/duplicate
