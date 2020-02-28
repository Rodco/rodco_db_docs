# supplier:

Table
name
country
phone
website
credit_term
credit_limit
is_shipping_supplier

Actions
create

# supplier_credit_note:

Table
received_at
created_at
updated_at
supplier_id
applied_at
currency
total
balance
status
archived
payment_status

Actions
Create
Approve

# suppler_debit_note:

Table

created_at
updated_at
supplier_id
applied_at
currency
total
balance
received_at
status

payment_status

Actions
Create
Approve

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
balance
payment_status

dropdown with accordion to show supplier_invoice_item's and supplier_invoice_item_received

Actions
Create
Approve

# supplier_invoice_item:

Table
product_id
amount
price
discount
tax
supplier_invoice_id

# supplier_invoice_item_received:

Table
product_id
amount
supplier_invoice_id
