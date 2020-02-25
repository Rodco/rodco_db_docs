#### Bank:

* id
* name
* description
* balance

#### Bank_transfer:

* id
* source_bank_id
* destination_bank_id
* amount
* currency
* exchange_rate
* reason
* archived
* status
* approved_by_user_id
* applied_at

#### Bank_transfer_item:

* id
* bank_transfer_id
* sales_payment_item_id
* sales_payment_reversal_item_id
* amount


#### purchase_order:

* id
* created_at
* updated_at
* supplier_id
* ordered_at
* approved_by_user_id
* total
* credit_term
* quote_url
* expires_at
* notes
* ordered_by_user_id
* Items
* description
* archived
* status
* applied_at
* is_supplier_invoice

#### Expense_credit_note:
Credit note created by supplier

* Id
* Number
* code
* external_id
* supplier_id
* created_at
* updated_at
* applied_at
* payable_at
* invoice_date
* archived
* status
* Invoice_pdf
* Invoice_xml
* Invoice_xml_response
* Purchase_order_id
* Invoice_items (json)
* currency
* exchange_rate
* service_sub_total_taxed
* Service_sub_total_exempt
* service_sub_total_exonerated
* product_sub_total_taxed
* Product_sub_total_exempt
* product_sub_total_exonerated
* sub_total_taxed
* Sub_total_exempt
* sub_total_exonerated
* sub_total
* Discount_total
* sub_total_net
* tax_total
* tax_exception_json
* tax_exoneration_json
* Tax_total_returned
* total
* total_pending_payment
* payment_status

#### Expense_debit_note:
Debit note created by supplier

* Id
* Number
* code
* external_id
* supplier_id
* created_at
* updated_at
* Applied_at
* Received_at
* invoice_date
* archived
* status
* Invoice_pdf
* Invoice_xml
* Invoice_xml_response
* Purchase_order_id
* Invoice_items (json)
* currency
* exchange_rate
* service_sub_total_taxed
* Service_sub_total_exempt
* service_sub_total_exonerated
* product_sub_total_taxed
* Product_sub_total_exempt
* product_sub_total_exonerated
* sub_total_taxed
* Sub_total_exempt
* sub_total_exonerated
* sub_total
* Discount_total
* sub_total_net
* tax_total
* tax_exception_json
* tax_exoneration_json
* Tax_total_returned
* total
* Total_pending_payment
* payment_status

#### expense_invoce:

* id
* Number
* code 
* external_id ?
* supplier_id
* created_at
* updated_at
* applied_at
* received_at
* archived
* status
* invoice_date
* invoice_pdf
* invoice_xml
* invoice_xml_response
* eletronic_invoice_response
* purchase_order_id 
* invoice_items (json)
* currency
* exchange_rate
* service_sub_total_taxed
* service_sub_total_exempt
* service_sub_total_exonerated
* product_sub_total_taxed
* product_sub_total_exempt
* product_sub_total_exonerated
* sub_total_taxed
* sub_total_exempt
* sub_total_exonerated
* sub_total
* discount_total
* sub_total_net
* tax_total
* tax_exception_json
* tax_exoneration_json
* tax_total_returned
* total
* total_pending_payment
* is_credit
* reference_document
* regulation 
* payment_status
* schedule_at
* expires_at 

#### expense_payment:

* Id
* number
* external_id
* Supplier_id
* currency
* exchange_rate
* created_at
* updated_at
* Applied_at
* Received_at
* reference
* Approved_payment_at
* archived
* Status

#### expense_payment_item:

* Id
* expense_payment_id
* expense_invoice_id
* expense_credit_note_id
* expense_debit_note_id
* total

#### expense_payment_reversal:

* Id
* number
* external_id
* supplier_id
* created_at
* updated_at
* applied_at
* received_at
* archived
* status
* total

#### expense_payment_reversal_item:

* Id
* expense_payment_reversal_id
* expense_invoice_id
* expense_credit_note_id
* expense_debit_note_id
* total

#### expense_ticket_invoce:

* id
* Number
* code 
* external_id 
* supplier_id
* created_at
* updated_at
* applied_at
* received_at
* archived
* status
* invoice_date
* invoice_pdf
* invoice_xml
* invoice_xml_response
* eletronic_invoice_response
* purchase_order_id 
* invoice_items (json)
* currency
* exchange_rate
* service_sub_total_taxed
* service_sub_total_exempt
* service_sub_total_exonerated
* product_sub_total_taxed
* product_sub_total_exempt
* product_sub_total_exonerated
* sub_total_taxed
* sub_total_exempt
* sub_total_exonerated
* sub_total
* discount_total
* sub_total_net
* tax_total
* tax_exception_json
* tax_exoneration_json
* tax_total_returned
* total
* total_pending_payment
* is_credit
* reference_document
* regulation 

#### supplier_payment:

* id
* approved_payment_date
* number
* external_id
* supplier_id
* created_at
* updated_at
* applied_at
* received_at
* archived
* status

#### supplier_payment_item:

* Id
* supplier_payment_id
* supplier_invoice_id
* supplier_credit_note_id
* supplier_debit_note_id
* total

#### supplier_payment_reversal:

* id
* approved_payment_date
* number
* external_id
* supplier_id
* created_at
* updated_at
* applied_at
* received_at
* archived
* status
* total

#### supplier_payment_reversal_id:

* Id
* supplier_payment_id
* supplier_invoice_id
* supplier_credit_note_id
* supplier_debit_note_id
* total