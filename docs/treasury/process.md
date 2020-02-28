# Bank:

# Bank_transfer:

on approve
transfer balance between items

# purchase_order:

on approve
if it's supply invoice, creare supply invoice, supply invoiceitems and receive_items
otherwise just maked as archived

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
