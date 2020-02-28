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

#### payable_credit_note:

Credit note created by supplier

- Id
- Number
- readable_number
- code
- external_id
- supplier_id [*]
- created_at
- updated_at
- applied_at
- payable_at
- invoice_date [*]
- archived
- status
- Invoice_pdf [*]
- Invoice_xml
- Invoice_xml_response
- Purchase_order_id
- Invoice_items (json)
- currency [*]
- exchange_rate [*]
- service_sub_total_taxed [*]
- Service_sub_total_exempt [*]
- service_sub_total_exonerated [*]
- product_sub_total_taxed [*]
- Product_sub_total_exempt [*]
- product_sub_total_exonerated [*]
- sub_total_taxed [*]
- Sub_total_exempt [*]
- sub_total_exonerated [*]
- sub_total [*]
- Discount_total [*]
- sub_total_net [*]
- tax_total [*]
- tax_exception_json
- tax_exoneration_json
- Tax_total_returned
- total [*]
- balance
- payment_status
- api_source [*]

#### Expense_debit_note:

Debit note created by supplier

- Id
- Number
- readable_number
- code
- external_id
- supplier_id [*]
- created_at
- updated_at
- Applied_at
- Received_at
- invoice_date [*]
- archived
- status
- Invoice_pdf [*]
- Invoice_xml
- Invoice_xml_response
- Purchase_order_id
- Invoice_items (json)
- currency [*]
- exchange_rate [*]
- service_sub_total_taxed [*]
- Service_sub_total_exempt [*]
- service_sub_total_exonerated [*]
- product_sub_total_taxed [*]
- Product_sub_total_exempt [*]
- product_sub_total_exonerated [*]
- sub_total_taxed [*]
- Sub_total_exempt [*]
- sub_total_exonerated [*]
- sub_total [*]
- Discount_total [*]
- sub_total_net [*]
- tax_total [*]
- tax_exception_json
- tax_exoneration_json
- Tax_total_returned
- total [*]
- balance [*]
- payment_status
- api_source [*]

#### expense_invoce:

- id
- Number [*]
- code [*]
- readable_number
- external_id ?
- supplier_id [*]
- created_at
- updated_at
- applied_at
- received_at
- archived
- status
- invoice_date [*]
- invoice_pdf [*]
- invoice_xml
- invoice_xml_response
- eletronic_invoice_response
- purchase_order_id
- invoice_items (json)
- currency [*]
- exchange_rate [*]
- service_sub_total_taxed [*]
- service_sub_total_exempt [*]
- service_sub_total_exonerated [*]
- product_sub_total_taxed [*]
- product_sub_total_exempt [*]
- product_sub_total_exonerated [*]
- sub_total_taxed [*]
- sub_total_exempt [*]
- sub_total_exonerated [*]
- sub_total [*]
- discount_total [*]
- sub_total_net [*]
- tax_total [*]
- tax_exception_json
- tax_exoneration_json
- tax_total_returned
- total [*]
- balance
- is_credit
- reference_document
- regulation
- payment_status
- schedule_at
- expires_at
- api_source [*]

#### expense_ticket_invoce:

- id
- Number [*]
- code [*]
- external_id
- readable_number

* supplier_id
* created_at
* updated_at
* applied_at
* received_at
* archived
* status
* invoice_date [*]
* invoice_pdf
* invoice_xml
* invoice_xml_response
* eletronic_invoice_response
* purchase_order_id
* invoice_items (json)
* currency [*]
* exchange_rate [*]
* service_sub_total_taxed [*]
* service_sub_total_exempt [*]
* service_sub_total_exonerated [*]
* product_sub_total_taxed [*]
* product_sub_total_exempt [*]
* product_sub_total_exonerated [*]
* sub_total_taxed [*]
* sub_total_exempt [*]
* sub_total_exonerated [*]
* sub_total [*]
* discount_total [*]
* sub_total_net [*]
* tax_total [*]
* tax_exception_json
* tax_exoneration_json
* tax_total_returned
* total [*]
* balance
* is_credit
* reference_document
* regulation
* api_source [*]

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
- expense_invoice_id
- expense_credit_note_id
- expense_debit_note_id
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
- expense_invoice_id
- expense_credit_note_id
- expense_debit_note_id
- api_source [*]
