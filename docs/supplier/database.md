#### supplier:

- id
- name [*]
- identification [*]
- identification_type [*]
- country [*]
- province
- city
- address
- postalCode
- phone [*]
- website
- credit_term [\*](0,>=0)
- credit_limit [\*](0,>=0)
- is_shipping_supplier (false)
- api_source [*]

#### supplier_credit_note:

- Id
- created_at
- updated_at
- supplier_id [*]
- applied_at
- currency [*]
- exchange_rate [*] (1, >0)
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
- balance [*]
- received_at
- status
- archived
- payment_status
- items_json
- code
- number
- api_source [*]
- readable_number

#### suppler_debit_note:

- id
- created_at
- updated_at
- supplier_id
- applied_at
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
- balance [*]
- received_at
- status
- archived
- payment_status
- items_json
- code
- number
- readable_number
- api_source

#### supplier_invoice:

- id
- created_at
- updated_at
- supplier_id
- applied_at
- received_at
- ordered_at
- purchase_order_id [*]
- status
- product_warehouse_id [*]
- archived
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
- balance [*]
- payment_status
- items_json
- code
- number
- readable_number
- schedule_at
- expires_at
- api_source [*]

#### supplier_invoice_item:

- id
- product_id [*]
- amount [*] >0
- price [*] >0
- discount [*] >=0
- tax [*] >=0
- supplier_invoice_id [*]
- api_source [*]

#### supplier_invoice_item_received

- id
- product_id [*]
- amount [*] >0
- supplier_invoice_id [*]
- api_source [*]
- cost
