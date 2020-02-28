# supplier:

User Cases

- Reps from multiple departmanets must create and update suppliers.
- Reps must search for and filter by name and is_shipping_supplier

Table
name [R,F,C*]
country [R,F,C*]
phone
website
credit_term [R,F,C*] {0}
credit_limit [R,F,C*] {0}
is_shipping_supplier [R,F] {false}

Actions
create

# supplier_credit_note:

- Treasure Reps need to create international only supplier_credit_note when suppliers issue them.
- Tresure Reps need to upload pdf, xml and response_xml files manually in case they are not received automatically. ( The system updates the details automatically form xml files )
- Treasure Reps want to search and filter credit notes to answer specific questions like what's it's balance or when was it created.
- Finance Reps want to approve supplier_credit_note so they become active in the system and available in payments.

Table
received_at
created_at
updated_at
supplier_id [R,F,C*]
applied_at
currency [R,F,C*]
total [R,F,C*]
balance [R,F]
status [R,F]
archived
payment_status [R,F]

Actions
Create
Approve

# supplier_debit_note:

- Treasure Reps need to create international only supplier_credit_note when suppliers issue them.
- Tresure Reps need to upload pdf, xml and response_xml files manually in case they are not received automatically. ( The system updates the details automatically form xml files )
- Treasure Reps want to search and filter credit notes to answer specific questions like what's it's balance or when was it created.
- Finance Reps want to approve supplier_credit_note so they become active in the system and available in payments.

Table

created_at
updated_at
supplier_id [R,F,C*]
applied_at
currency [R,F,C*]
total [R,F,C*]
balance [R,F,C*]
received_at [R,F]
status [R,F]
archived
payment_status [R,F]

Actions
Create
Approve

# supplier_invoice:

- Tresure Reps need to upload pdf, xml and response_xml files manually in case they are not received automatically. ( The system updates the details automatically form xml files )
- Treasure Reps want to search and filter supplier_invoices to answer specific questions about their state
- Managment want to update international supplier_invoice price and tax information. Only they can see this information and this only applies to international invoices.
- All reps want to see the supplier_invoice and supplier_invoice_items_received in a dropdown on row click.

Table
created_at
updated_at
supplier_id [R,F,C*]
applied_at [R,F]
received_at [R,F]
ordered_at [R,F,C*]
purchase_order_id [R,F,C*]
status [R,F]
product_warehouse_id [R,F,C*]
archived
currency [R,F,C*]
total [R,F,C*]
balance
payment_status

Actions
Create
Approve
