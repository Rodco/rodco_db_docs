# sales_credit_note

Credit notes created for customers when they return products or require financial discounts. Also used to "void" sales invoices that were reject by tax authority.

There are threee kinds of Sales Credit Notes

1. Financial Credit Notes: This credit notes are created manually, only the total amount field is neccesary.
2. Returns
3. Credit Notes to Void an Invoice

- Trigger
  - don't allow total_pending_payment below 0

on_update trigger

- validate that approved_by_billing_user_id and approved_by_office_user_id are set.

on archived=true

- set applied_at, status, total_pending_payment
- if financial credit_note then set fields accordingly. [TODO:complete field details]
- create sales_credit_note_item for each entry in items

# sales_credit_note_item:

Used for history and calculations

# sales_debit_note:

Debit notes created for customers they require custom fees.. Also used to "void" sales credit notes that were reject by tax authority.

There are two kinds of Sales Debit Notes

1. Financial Notes: This notes are created manually, only the total amount field is neccesary.
2. Debit Notes to Void a Credit Note

- Trigger
  - don't allow total_pending_payment below 0

on_update trigger

- validate that approved_by_billing_user_id and approved_by_office_user_id are set.

on archived=true

- set applied_at, status, total_pending_payment
- if financial debit_note then set fields accordingly. [TODO:complete field details]
- create sales_debit_note_item for each entry in items

# sales_debit_note_item:

Used for history and calculations

# sales_payment:

Sales payments are created for cash, credit card, bank transfers and check payments.

- Trigger
  - don't allow sales_payment_item.total below 0

on archived=true

- set applied_at, status
- update total_pending_amount for each entry in items json.
- create sales_payment_item for each entry in items

# sales_payment_item:

Used for history and calculations

# sales_payment_reversal:

Created to reverse and incorrect payment.

- Trigger
  - don't allow sales_payment_reserval_item.total below 0

on archived=true

- set applied_at, status
- update total_pending_amount for each entry in items json.
- create sales_payment_reserval_item for each entry in items

# sales_payment_reserval_item:

Used for history and calculations
