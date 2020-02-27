#### sales_credit_note

- Id
- created_at
- updated_at
- number
- readable_number
- code
- applied_at
- archived
- credit_term
- customer_id [*]
- customer_rep_id [*]
- approved_by_billing_user_id
- approved_by_office_user_id
- void_sales_credit_note_id: (This note was created in replacement of referenced id.)
- replacement_sales_credit_note_id: (Referenced id replace this note.)
- pdf_url
- xml_url
- xml_validation_url
- currency
- exchange_rate
- service_sub_total_taxed
- service_sub_total_exempt
- service_sub_total_exonerated
- product_sub_total_taxed
- product_sub_total_exempt
- product_sub_total_exonerated
- sub_total_taxed
- sub_total_exempt
- sub_total_exonerated
- sub_total
- discount_total
- sub_total_net
- tax_total
- tax_exception_json
- tax_exoneration_json
- tax_total_returned
- total [*] >0
- balance [*] >=0 createTrigger = total
- public_notes
- private_notes
- payment_form
- payment_status
- items_json
- api_source

#### sales_credit_note_item:

- id
- product_id
- price [*] ( > 0 )
- amount [*] ( > 0 )
- discount_rate [*] (>= 0 && <= 100)
- product_tax_id [*]
- api_source [*]

#### sales_debit_note:

- Id
- created_at
- updated_at
- number
- readable_number
- code
- applied_at
- credit_term
- customer_id [*]
- customer_rep_id [*]
- approved_by_billing_user_id
- approved_by_office_user_id
- void_sales_debit_note_id
- replacement_sales_debit_note_id
- pdf_url
- xml_url
- xml_validation_url
- currency
- exchange_rate
- service_sub_total_taxed
- service_sub_total_exempt
- service_sub_total_exonerated
- product_sub_total_taxed
- product_sub_total_exempt
- product_sub_total_exonerated
- sub_total_taxed
- sub_total_exempt
- sub_total_exonerated
- sub_total
- discount_total
- sub_total_net
- tax_total
- tax_exception_json
- tax_exoneration_json
- tax_total_returned
- balance [*] (>= 0) createTrigger = total
- public_notes
- private_notes
- payment_form
- payment_status
- items_json
- api_source [*]
- total [*]

#### sales_debit_note_item:

- Id
- product_id [*]
- price [*] ( > 0 )
- amount [*] ( > 0 )
- discount_rate (>=0 && <100)
- product_tax_id [*]
- api_source [*]

#### sales_payment:

- Id
- number
- readable_number
- external_id
- customer_id [*]
- created_at
- updated_at
- applied_at
- received_at
- archived
- status
- customer_rep_id [*]
- created_by_user_id
- confirmed_by_user_id
- deposited_in_bank_id [*]
- items_json
- api_source [*]
- total [*]

#### sales_payment_item:

- id
- sales_payment_id
- sales_invoice_id
- sales_credit_note_id
- sales_debit_note_id
- total [*] ( > 0)
- api_source [*]

#### sales_payment_reversal:

- Id
- number [*]
- external_id
- customer_id [*]
- created_at
- updated_at
- applied_at
- received_at
- archived
- status
- customer_rep_id [*]
- created_by_user_id [*]
- confirmed_by_user_id
- sourced_from_bank_id [*]
- items_json
- total [*] (> 0)
- api_source [*]

#### sales_payment_reserval_item:

- id
- sales_payment_reversal_id [*]
- sales_invoice_id [*]
- sales_credit_note_id
- sales_debit_note_id
- total [*] (> 0)
- api_source [*]
- product_tax_id
