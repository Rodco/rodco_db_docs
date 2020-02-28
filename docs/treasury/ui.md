# Bank:

User Cases

- Treasurey Reps must create and update banks or cashiers in order to store money

Table

- id
- name [R,F,C*]
- description
- balance [R,F]
- api_source

Actions
Create

# Bank_transfer:

- Treasury Reps must create and update bank transfers in order to move money from one bank to another.
- Treasury Reps want to review Bank_transfers created from sales payments.
- Financial Reps must approve bank transfers to make them active on the system.
- Both Reps would like to search and filter bank transfers and view a dropdown of the bank_transfer_items.

Table:

- source_bank_id [R,F,C*]
- destination_bank_id [R,F,C*]
- amount [R,F,C*]
- currency [R,F,C*] {\$,EU,C/}
- reason [R,F,C*]
- status {draft}
- approved_by_user_id [R,F]
- applied_at [R,F]

Actions
Approve

# purchase_order:

- Managment users must create and update purchase orders for supplier product orders
- Leadership Reps ( marketing, sales, logisitics, imports ) must create purchase orders for their expenses
- Managment users must approve purchase orders above \$500
- Treasury reps must approve purchase orders below \$500
- Once approved treasury reps must turn supplier purchase order into suplier_invoices

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

- The system automatically creates expense notes from notes sent electronically
- Treasury Reps must approve notes once all documents ( pdf,xml and response_xml ) have arrieved in order to include them in the system.
- Tresury Reps must be able to search and filter for specific information about the notes.
- Tresury Reps must be able to click on the ( pdf,xml and response_xml ) and open a new window to see the document contents.

Table
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

# Expense_debit_note:

- The system automatically creates expense notes from notes sent electronically
- Treasury Reps must approve notes once all documents ( pdf,xml and response_xml ) have arrieved in order to include them in the system.
- Tresury Reps must be able to search and filter for specific information about the notes.
- Tresury Reps must be able to click on the ( pdf,xml and response_xml ) and open a new window to see the document contents.

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

- The system automatically creates expense notes from notes sent electronically
- Treasury Reps must link the invoice with all required documentation ( pdf,xml and response_xml ) to an existing and approved purchase order in order to activate it in the system.
- Tresury Reps must be able to search and filter for specific information about the notes.
- Tresury Reps must be able to click on the ( pdf,xml and response_xml ) and open a new window to see the document contents.

Table

Number [R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
status [R,F]
invoice_date [R,F]
invoice_pdf [R,F]

invoice_xml
purchase_order_id [R,F]
invoice_items (json)
currency [R,F]
total [R,F]
balance [R,F]
is_credit [R,F]
payment_status [R,F]

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

Number [R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
readable_number

archived
status [R,F]
invoice_date [R,F]
invoice_pdf [R,F]
invoice_xml
invoice_xml_response
currency [R,F]
total [R,F]

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
