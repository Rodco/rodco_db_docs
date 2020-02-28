# electronic_document_log

Created by the serverless system.
There are no updates, deletes or creates.

- Actions
  - void
    - check that the status is rejected
    - create a document that reverts the selected document

# sales_invoce:

Sales Invoices are created by the serverless system.
There are no updates, deletes or creates.

- Trigger

  - don't allow balance below 0

- Actions
  - resend
    re-send invoice to customers email
  - return
    - check that amount_returned <= to amount
    - create sales_credit_note with sales_credit_note_items

# sales_invoce_item:

Sales Invoices are created by the serverless system.
There are no updates, deletes or creates.

# product_price_list:

id
name
markup
discount

# product_price_list_item:

id
product_id
markup
price_type
product_price_list_id
discount

# product_price_list_customer

    * on update
        update customer.price_lists

# quote:

id
created_at
updated_at
applied_at
customer_id
shipping_supplier_id
status
customer_rep_id
customer_order_number
credit_term
currency
exchange_rate
shipping_date
items_json
tax_exception_json
tax_exoneration_json
order_id
customer_override_type
customer_override_identification
customer_override_email_for_invoce
total
requires_office_approval
approved_by_office_user_id
approved_by_office_at
description
origin

# order:

Order

id
created_at
updated_at
applied_at
customer_id
shipping_supplier_id
status
customer_rep_id
customer_order_number
approved_by_billing_user_id
approved_by_billing_at
approved_by_billing_status
credit_term
currency
exchange_rate
shipping_date
order_items_json
tax_exception_json
tax_exoneration_json
sales_invoce_id
quote_id
customer_override_type
customer_override_identification
customer_override_email_for_invoce
total
requires_office_approval
approved_by_office_user_id
approved_by_office_at
approved_by_office_status
replaces_sales_invoce_id
description
origin
