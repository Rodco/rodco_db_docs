#### electronic_document_log

- id
- document_id [*]
- type [*]
- code [*]
- status [*]
- response [*]
- api_source [*]

#### product_price_list:

- id
- name [*]
- markup [*]
- api_source [*]

#### product_price_list_item:

- id
- product_id [*]
- markup [*]
- price_type [*] {markup}
- product_price_list_id [*]
- api_source [*]

#### quote:

- id
- created_at
- updated_at
- applied_at
- customer_id [*]
- shipping_supplier_id
- status
- customer_rep_id
- customer_order_number
- credit_term [*] >=0
- currency [*]
- exchange_rate [*] > 0
- shipping_date
- quote_items_json
- tax_exception_json
- tax_exoneration_json
- order_id
- customer_override_type
- customer_override_identification
- customer_override_email_for_invoce
- order_total [*] >0
- requires_office_approval
- approved_by_office_user_id
- approved_by_office_at
- description
- origin [*]
- api_source [*]

#### order:

- id
- created_at
- updated_at
- applied_at
- customer_id [*]
- shipping_supplier_id
- status (draft)
- customer_rep_id
- customer_order_number
- approved_by_billing_user_id
- approved_by_billing_at
- approved_by_billing_status
- credit_term [*]
- currency [*]
- exchange_rate [*] > 0
- shipping_date
- items_json
- tax_exception_json
- tax_exoneration_json
- sales_invoce_id
- quote_id
- customer_override_type
- customer_override_identification
- customer_override_email_for_invoce
- order_total [*]
- requires_office_approval
- approved_by_office_user_id
- approved_by_office_at
- approved_by_office_status
- replaces_sales_invoce_id
- description
- origin [*]
- archived
- api_source [*]

#### sales_invoce:

- id
- created_at
- updated_at
- number [*]
- readable_number
- code [*]
- applied_at
- credit_term [*]
- order_id [*]
- customer_id [*]
- shipping_supplier_id
- shipping_tracking_number
- customer_rep_id
- approved_by_billing_user_id
- approved_by_office_user_id
- void_sales_invoce_id
- replacement_sales_invoce_id
- pdf_url
- xml_url
- xml_validation_url
- currency [*]
- exchange_rate [*] > 0
- service_sub_total_taxed [*] >= 0
- Service_sub_total_exempt [*] >= 0
- service_sub_total_exonerated [*] >= 0
- product_sub_total_taxed [*] >= 0
- Product_sub_total_exempt [*] >= 0
- product_sub_total_exonerated [*] >= 0
- sub_total_taxed [*] >= 0
- Sub_total_exempt [*] >= 0
- sub_total_exonerated [*] >= 0
- sub_total [*] >= 0
- Discount_total [*] >= 0
- sub_total_net [*] >= 0
- tax_total [*] >= 0
- tax_exception_json
- tax_exoneration_json
- Tax_total_returned
- total [*] >= 0
- balance [*] >= 0
- public_notes
- private_notes
- payment_form [*]
- payment_status
- items_json
- api_source [*]

#### sales_invoce_item:

- Id
- created_at
- updated_at
- sales_invoce_id [*]
- product_id [*]
- product_warehouse_id [*]
- unit_price [*] >= 0
- amount [*] >= 0
- discount_rate [*] >= 0
- product_tax_id [*]
- tax_rate [*] >= 0
- product_cost_id [*]
- discount_reason
- amount_return {0}
- api_source [*]
