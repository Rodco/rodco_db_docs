# Bank:

Table

- id
- name [R,F,C*]
- description
- balance [R,F]
- api_source

Actions
Create

# Bank_transfer:

Table:

- source_bank_id [R,F,C*]
- destination_bank_id [R,F,C*]
- amount [R,F,C*]
- currency [R,F,C*] {\$,EU,C/}
- reason [R,F,C*]
- status {draft}
- approved_by_user_id [R,F]
- applied_at [R,F]

Display drop down accordion with Bank_transfer_item's
Actions
Approve

# purchase_order:

Table

- created_at
- supplier_id [R,F,C*]
- ordered_at [R,F,C*]
- approved_by_user_id [R,F]
- total [R,F,C*]
- credit_term [R,F,C*]
- quote_url [R,F,C*]
- expires_at [R,F,C*]
- ordered_by_user_id [R,F]
- description [R,F,C*]
- status [R,F]
- applied_at
- is_supplier_invoice [R,F,C*]

Actions
Approve ( as supplier or expense )

# Expense_credit_note:

Table
<<<<<<< HEAD
Number [R,F]
readable_number [R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]

archived
status [R,F]
Invoice_pdf [R,F]
currency [R,F]
total [R,F]
balance [R,F]
payment_status [R,F]

Show details in droppdown accordion

# Expense_debit_note:

Table
code [R,F]
supplier_id [R,F]
created_at [R,F]
Applied_at [R,F]
invoice_date [R,F]
archived
status [R,F]
Invoice_pdf [R,F]
currency [R,F]
total [R,F]
balance [R,F]
payment_status [R,F]

Show details in droppdown accordion

# expense_invoce:

Table

<<<<<<< HEAD
Number [R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
status [R,F]
invoice_date [R,F]
invoice_pdf [R,F]
=======
Number
readable_number
supplier_id
created_at
applied_at
status
invoice_date
invoice_pdf

> > > > > > > 8b1899b80b4f1ddae0fcd3f54799bfefb76467c4
> > > > > > > invoice_xml
> > > > > > > purchase_order_id [R,F]
> > > > > > > invoice_items (json)
> > > > > > > currency [R,F]
> > > > > > > total [R,F]
> > > > > > > balance [R,F]
> > > > > > > is_credit [R,F]
> > > > > > > payment_status [R,F]

Show invoice_items (json) on dropdown accordion

Actions

# expense_payment:

Table

Supplier_id [R,F]
currency [R,F]
Applied_at [R,F]
reference [R,F]
archived [R,F]
Status [R,F]

Show expense_payment_item on dropdown accordion

Actions
Revert
Approve

# expense_payment_reversal:

Table

supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
archived [R,F]
status [R,F]

# expense_ticket_invoce:

Table

<<<<<<< HEAD
Number [R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
=======
Number
readable_number
supplier_id
created_at
applied_at

> > > > > > > 8b1899b80b4f1ddae0fcd3f54799bfefb76467c4
> > > > > > > archived
> > > > > > > status [R,F]
> > > > > > > invoice_date [R,F]
> > > > > > > invoice_pdf [R,F]
> > > > > > > invoice_xml
> > > > > > > invoice_xml_response
> > > > > > > currency [R,F]
> > > > > > > total [R,F]

Show invoice_items (json) in dropdown accordion

Actions
Approve

# supplier_payment:

Table

number [R,F]
readable_number[R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
approved_payment_date [R,F]

archived
status [R,F]

Show supplier_payment_item on dropdown accordion

Actions
Approve
Revert

# supplier_payment_reversal:

Table

number [R,F]
readable_number
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
status [R,F]
total [R,F]

Show supplier_payment_reversal_id on dropdown accordion

Actions
Approve
