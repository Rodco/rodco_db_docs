# Bank:

Table
Guessable CRUD

# Bank_transfer:

Table: Display drop down accordion with Bank_transfer_item's
Actions
Approve

# Bank_transfer_item:

Table: Standard with releted fields

# purchase_order:

Actions
Approve

# Expense_credit_note:

Table
Number
supplier_id
created_at
applied_at
archived
status
Invoice_pdf
Invoice_items (json)
currency
total
total_pending_payment
payment_status

# Expense_debit_note:

Table

Number
supplier_id
created_at
Applied_at
archived
status
Invoice_pdf
Invoice_items (json)
currency
total
Total_pending_payment
payment_status

Actions

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
total_pending_payment
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

table

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

Actions
Approve

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
received_at
archived
status
invoice_date
eletronic_invoice_response
currency
total
total_pending_payment
is_credit
reference_document
regulation

Show invoice_items (json) in dropdown accordion

# supplier_payment:

id
approved_payment_date
number
external_id
supplier_id
created_at
updated_at
applied_at
received_at
archived
status

# supplier_payment_item:

Id
supplier_payment_id
supplier_invoice_id
supplier_credit_note_id
supplier_debit_note_id
total

# supplier_payment_reversal:

id
approved_payment_date
number
external_id
supplier_id
created_at
updated_at
applied_at
received_at
archived
status

# supplier_payment_reversal_id:

Id
supplier_payment_id
supplier_invoice_id
supplier_credit_note_id
supplier_debit_note_id
total
