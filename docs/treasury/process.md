# Bank:

# Bank_transfer:

on approve
transfer balance between items

# purchase_order:

on approve
if it's supply invoice, creare supply invoice, supply invoiceitems and receive_items
otherwise just maked as archived

# Expense_credit_note:

on approve
check that it has all required files (pdf,xml and xml response)
check permissions and set archived=true and applied_at

# Expense_debit_note:

on approve
check that it has all required files (pdf,xml and xml response)
check permissions and set archived=true and applied_at

# expense_invoce:

on approve
check that it has all required files (pdf,xml and xml response)
check permissions and set archived=true and applied_at

# expense_payment:

on approve
for each item, modify pending_total
set archived=true and applied_at

on revert
check that payment is archived
create a expense_payment_reversal from current payment
for each item, modify pending_total
set archived=true and applied_at

# expense_payment_item:

# expense_payment_reversal:

on approve
for each item, modify pending_total
set archived=true and applied_at

# expense_payment_reversal_item:

# expense_ticket_invoce:

on approve
check that it has all required files (pdf,xml and xml response)
check permissions and set archived=true and applied_at

# supplier_payment:
on approve
check that it's approved to be paid at such date
reduce pending_total from each item in supplier_payment_item
set archived=true and applied_at

on reverse
check that it's approved to be paid at such date
reduce pending_total from each item in supplier_payment_item
set archived=true and applied_at

# supplier_payment_item:

# supplier_payment_reversal:

on approve
check that it's approved to be paid at such date
reduce pending_total from each item in supplier_payment_item
set archived=true and applied_at

# supplier_payment_reversal_item:

Id
supplier_payment_id
supplier_invoice_id
supplier_credit_note_id
supplier_debit_note_id
total
