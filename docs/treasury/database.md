#### Bank:

- id
- name [*]
- description
- balance [*] {0}
- api_source [*]

#### Bank_transfer:

- id
- source_bank_id [*]
- destination_bank_id [*]
- amount [*]
- currency [*]
- exchange_rate [*]
- reason [*]
- archived
- status
- approved_by_user_id
- applied_at
- api_source [*]

#### Bank_transfer_item:

- id
- bank_transfer_id [*]
- sales_payment_item_id [*]
- sales_payment_reversal_item_id [*]
- amount [*]
- api_source [*]

#### purchase_order:

- id
- created_at
- updated_at
- supplier_id [*]
- ordered_at [*]
- approved_by_user_id
- total [*]
- credit_term [*]
- quote_url
- expires_at [*]
- notes
- ordered_by_user_id [*]
- Items
- description [*]
- archived
- status
- applied_at
- is_supplier_invoice
- api_source [*]
- is_international

#### supplier_payment:

- id
- approved_payment_date
- number
- readable_number
- external_id
- supplier_id [*]
- created_at
- updated_at
- applied_at
- received_at
- archived
- status
- api_source [*]
- payment_form
- payment_reference
- total

#### supplier_payment_item:

- Id
- supplier_payment_id [*]
- supplier_invoice_id
- supplier_credit_note_id
- supplier_debit_note_id
- total [*]
- api_source [*]

#### supplier_payment_reversal:

- id
- approved_payment_date

- number
- readable_number

- external_id
- supplier_id [*]
- created_at
- updated_at
- applied_at
- received_at
- archived
- status
- total [*]
- api_source [*]
- payment_form
- payment_reference

#### supplier_payment_reversal_item:

- Id
- supplier_payment_id [*]
- supplier_invoice_id
- supplier_credit_note_id
- supplier_debit_note_id
- total [*]
- api_source [*]
