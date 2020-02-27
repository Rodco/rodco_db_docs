### Credit Note

#### Table

- Id
- created_at [R,F]
- applied_at [R,F]
- customer_id [R,F,C*]
- customer*rep_id [R,F] \_Autoselect from customer_id*
- approved_by_billing_user_id [R,F]
- approved_by_office_user_id [R,F]
- pdf_url [R]
- total [R,C*] ( > 0 )
- balance [R,C](>=0)
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

  - Should show items in dropdown accordion if it's archived=false
  - Should show sales_note_item in dropdown accordion if it's archived=true

* Actions:
  - Create ( customer_id, currency, exchange_rate, total, description )
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

    - Should show items in dropdown accordion if it's archived=false
    - Should show sales_note_item in dropdown accordion if it's archived=true

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

  - Actions:

    - Hold
      - set approved_by_billing_status = hold
    - Approve
      - set approved_by_billing_status= approved
      - set approved_by_billing_user_id
      - set approved_by_billing_at
