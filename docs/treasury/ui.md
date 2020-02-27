# Bank:

Table

- id
- name
- description
- balance
- api_source

Actions
Create

# Bank_transfer:

Table:

- source_bank_id
- destination_bank_id
- amount
- currency
- reason
- status
- approved_by_user_id
- applied_at

Display drop down accordion with Bank_transfer_item's
Actions
Approve

# Bank_transfer_item:

Table:

- id
- bank_transfer_id
- sales_payment_item_id
- sales_payment_reversal_item_id
- amount

# purchase_order:

Table

- created_at
- supplier_id
- ordered_at
- approved_by_user_id
- total
- credit_term
- quote_url
- expires_at
- ordered_by_user_id
- description
- status
- applied_at
- is_supplier_invoice

Actions
Approve ( as supplier or expense )

# Expense_credit_note:

Table
Number
supplier_id
created_at
applied_at
archived
status
Invoice_pdf
currency
total
balance
payment_status

Show details in droppdown accordion

# Expense_debit_note:

Table
code
supplier_id
created_at
Applied_at
invoice_date
archived
status
Invoice_pdf
currency
total
balance
payment_status

Show details in droppdown accordion

# expense_invoce:

Table

Number
supplier_id
created_at
applied_at
status
invoice_date
invoice_pdf
invoice_xml
purchase_order_id
invoice_items (json)
currency
total
balance
is_credit
payment_status

Show invoice_items (json) on dropdown accordion

Actions

# expense_payment:

Table

Supplier_id
currency
Applied_at
reference
archived
Status

Show expense_payment_item on dropdown accordion

Actions
Revert
Approve

# expense_payment_item:

Table

expense_payment_id
expense_invoice_id
expense_credit_note_id
expense_debit_note_id
total

# expense_payment_reversal:

Table

supplier_id
created_at
applied_at
archived
status

# expense_payment_reversal_item:

Table

expense_payment_reversal_id
expense_invoice_id
expense_credit_note_id
expense_debit_note_id
total

# expense_ticket_invoce:

Table

Number
supplier_id
created_at
applied_at
archived
status
invoice_date
invoice_pdf
invoice_xml
invoice_xml_response
currency
total

Show invoice_items (json) in dropdown accordion

Actions
Approve

# supplier_payment:

Table

number
supplier_id
created_at
applied_at
approved_payment_date
archived
status

Show supplier_payment_item on dropdown accordion

Actions
Approve
Revert

# supplier_payment_item:

Table

supplier_payment_id
supplier_invoice_id
supplier_credit_note_id
supplier_debit_note_id
total

# supplier_payment_reversal:

Table

number
supplier_id
created_at
applied_at
archived
status
total

Show supplier_payment_reversal_id on dropdown accordion

Actions
Approve

# supplier_payment_reversal_item:

Table
supplier_payment_id
supplier_invoice_id
supplier_credit_note_id
supplier_debit_note_id
total
