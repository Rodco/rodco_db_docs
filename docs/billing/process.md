# sales_credit_note

created for customers when they return products or require financial discounts. Also used to "void" sales invoices that were reject by tax authority.

There are threee kinds of Sales Credit Notes

1. Financial Credit Notes: This credit notes are created manually, only the total amount field is neccesary.
2. Returns
3. Credit Notes to Void an Invoice

- on archived=true

- set applied_at, status, balance
- if financial credit_note then set fields accordingly. [TODO:complete field details]
- create sales_credit_note_item for each entry in items

# sales_credit_note_item:

Used for history and calculations

# sales_payment:

Sales payments are created for cash, credit card, bank transfers and check payments.

on archived=true

- set applied_at, status
- update total_pending_amount for each entry in items json.
- create sales_payment_item for each entry in items

# sales_payment_item:

Used for history and calculations

# sales_payment_reversal:

Created to reverse and incorrect payment.

on archived=true

- set applied_at, status
- update total_pending_amount for each entry in items json.
- create sales_payment_reserval_item for each entry in items

# sales_payment_reserval_item:

Used for history and calculations