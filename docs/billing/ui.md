### Credit Note

#### Table

- Id
- created_at [R,F]
- applied_at [R,F]
- customer_id [R,F,C*]
- customer_rep_id [R,F]
- approved_by_billing_user_id [R,F]
- approved_by_office_user_id [R,F]
- pdf_url [R]
- total [R,C*] ( > 0 )
- balance [R]
- public_notes [R,F,C*]
- private_notes [C]

  - Table Details

    - Use component tableItemsDetails with sales_credit_note_item

  - Create/Update
    - when a customer_id is selected customer_rep_id should automatically be selected.

##### Actions:

- Create
- delete
  - if archived!=true

# Debit Note

- Table

  - created_at [R,F]
  - number [R,F]
  - readable_number
  - code
  - applied_at [R,F]
  - archived
  - customer_id [R,F,C*]
  - customer_rep_id [R,F]
  - approved_by_billing_user_id [R,F]
  - approved_by_office_user_id [R,F]
  - currency
  - total [R,F,C*]
  - balance [R,F]
  - items_json

  * Table Details
    Use component tableItemsDetails with sales_debit_note_item

  * Create/Update
    - when a customer_id is selected customer_rep_id should automatically be selected.

* Actions:
  - Create
  - delete
    - if archived!=true

# Sales_payment

- Table

  - number
  - readable_number
  - customer_id [R,F,C*]
  - created_at
  - applied_at
  - received_at
  - status
  - customer_rep_id
  - created_by_user_id
  - confirmed_by_user_id
  - deposited_in_bank_id [R,F,C*]
  - items_json
  - total [R,F]

  * Table Details

    - Use component tableItemsDetails with Sales_payment_item

  * Create

    - on create set created_by_user_id to the current user
    - on customer_id select set customer_rep_id from customer
    - use component salesInvoicePaymentSelector
      - load invoices when customer_id is selected
      - on update of amounts, update sales_payment.total and items_json

  * Update

    - do not allow customer_id changes
    - use component salesInvoicePaymentSelector
      - load invoices when customer_id is selected
      - on update of amounts, update sales_payment.total and items_json

* Actions:
  - apply
    - set archived=true
  - reverse
    - use mutation sales_payment_reverse(sales_payment_id)
  - delete
    - if archived!=true

# sales_payment_reversal

- Table

  - number
  - readable_number
  - customer_id [R,F,C*]
  - created_at
  - applied_at
  - received_at
  - status
  - customer_rep_id
  - created_by_user_id
  - confirmed_by_user_id
  - deposited_in_bank_id [R,F,C*]
  - items_json
  - total

  * Table Details
    - Use component tableItemsDetails with sales_payment_reversal

* Actions:

  - apply
    - set archived=true
  - delete
    - if archived!=true

* order approvals ( order )

  - Table

    - created_at [R,F]
    - applied_at
    - customer_id [R,F]
    - status [R,F]
    - customer_rep_id [R,F]
    - approved_by_billing_status [R,F]
    - credit_term [R,F]
    - currency
    - order_total [R,F]
    - requires_office_approval [R,F]
    - approved_by_office_status [R,F]

  - Table Details
    - Use component tableItemsDetails with orderDetails

- Actions:

  - Hold
    - set approved_by_billing_status = hold
  - Approve
    - set approved_by_billing_status= approved
    - set approved_by_billing_user_id
    - set approved_by_billing_at
