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

# product_price_list_item:

Table
product_id [name, brand, category, type]
markup
product_price_list_id
discount

Actions
Delete
Create
Update Bulk
Optional [Should show a modal to set the markup and discount for all selected prices]

# product_price_list_customer

Table
product_price_list_id
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

- Table:
  _ created_at
  _ updated*at
  * applied*at
  * customer*id
  * shipping*supplier_id
  * status
  _ customer_rep_id
  _ customer*order_number
  * approved_by_billing_user_id
  * approved_by_billing_at
  * approved_by_billing_status
  * credit*term
  * currency
  _ exchange_rate
  _ shipping*date
  * order*items_json
  * tax*exception_json
  * tax*exoneration_json
  * sales*invoce_id
  * quote*id
  * customer*override_type
  * customer*override_identification
  * customer*override_email_for_invoce
  * order*total
  * requires_office_approval
  * approved_by_office_user_id
  * approved_by_office_at
  * approved_by_office_status
  * replaces*sales_invoce_id
  * description \*
  origin

* Actions

  - Approve
    - if requires_office_approval 
    - must have approved_by_billing_user_id
    - archived=true must have approved_by_office_user_id

  - Duplicate
    - send order id to order/duplicate
