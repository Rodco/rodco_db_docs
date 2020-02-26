### Credit Note

#### Table

- Id
- created_at [R,F]
- applied_at [R,F]
- customer_id [R,F,C*]
- customer_rep_id [R,F] _Autoselect from customer_id_
- approved_by_billing_user_id [R,F]
- approved_by_office_user_id [R,F]
- pdf_url [R]
- total [R,C*] ( > 0 )
- total_pending_payment [R,C](>=0)
- public_notes [R,F,C*]
- private_notes [C]

##### Table Details

- Should show items in dropdown accordion if it's archived=false

  - Should show sales_note_item in dropdown accordion if it's archived=true

##### Actions:

- Create ( customer_id, currency, exchange_rate, total, description )
- delete
  - if archived!=true

# Debit Note

- Table

  - created_at
  - number
  - code
  - applied_at
  - archived
  - customer_id
  - customer_rep_id
  - approved_by_billing_user_id
  - approved_by_office_user_id
  - currency
  - total
  - total_pending_payment
  - items_json

* Table Details

  - Should show items in dropdown accordion if it's archived=false
  - Should show sales_note_item in dropdown accordion if it's archived=true

* Actions:
  - Create ( customer_id, currency, exchange_rate, total, description )
  - delete
    - if archived!=true

# Sales_payment

- Table

  - number
  - customer_id
  - created_at
  - applied_at
  - received_at
  - status
  - customer_rep_id
  - created_by_user_id
  - confirmed_by_user_id
  - deposited_in_bank_id
  - items_json

  * Table Details

    - Should show items in dropdown accordion if it's archived=false
    - Should show sales_note_item in dropdown accordion if it's archived=true

* Actions:
  - apply
    - set archived=true
  - delete
    - if archived!=true

# sales_payment_reversal

- Table

  - number
  - customer_id
  - created_at
  - applied_at
  - received_at
  - status
  - customer_rep_id
  - created_by_user_id
  - confirmed_by_user_id
  - deposited_in_bank_id
  - items_json

  * Table Details

    - Should show items in dropdown accordion if it's archived=false
    - Should show sales_note_item in dropdown accordion if it's archived=true

* Actions:

  - apply
    - set archived=true
  - delete
    - if archived!=true

* order approvals ( order )

  - Table

    - created_at
    - applied_at
    - customer_id
    - status
    - customer_rep_id
    - approved_by_billing_status
    - credit_term
    - currency
    - order_total
    - requires_office_approval
    - approved_by_office_status

  - Actions:

    - Hold
      - set approved_by_billing_status = hold
    - Approve
      - set approved_by_billing_status= approved
      - set approved_by_billing_user_id
      - set approved_by_billing_at
