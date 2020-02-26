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

Guessable CRUD

id
name
markup
discount

# product_price_list_item:

Table
product_id [name, brand, category, type]
markup
price_type
product_price_list_id
discount

Actions
Delete
Create

# product_price_list_customer

Table
product_price_list
customer_id

Actions
Create
Delete

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

Sales invoices should dropdown and display in accordion the list of sales_invoice_items.

Sales_Invoice_Items should have checkboxes or numeric inputs used to insert the amount of items to be returned. Max value of input should be the amount of sales_invoice_items.

- Actions
  - Resend
    - send sales_invoice_id to /sales_invoice/resend
  - Return
    - send sales_invoice_items id's and amounts to /sales_invoice/return

# Order

- Actions

  - Approve
    - send order id to order/approve
  - Duplicate
    - send order id to order/duplicate
