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
Approve ( as supplier )

# supplier_payment:

- Treasury Reps create supplier payments to propose when a payment will be made
- Treasure Reps can assign approved_payment_date for invoices less than \$300 or c/150,000
- Managment sets approved_payment_date for each invoice
- Treasure Reps approve payments when approved_payment_date has been reached and payment has been made.
- Treasure Reps can revert an archived payment if there is a mistake with it.
- Treasure Reps can delete payments not yet archived in order to create a new one or in case of error or unforseeable change.

Table

number [R,F]
readable_number[R,F]
supplier_id [R,F]
created_at [R,F]
applied_at [R,F]
approved_payment_date [R,F]

archived
status [R,F]
total

Show supplier_payment_item on dropdown accordion

Actions
Approve
Revert

# supplier_payment_reversal:


- Treasurey and Finance Reps can search, filter and look at details of supplier_payment_reversal and their items in order to answer specific questions about them.

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
