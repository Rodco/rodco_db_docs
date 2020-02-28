### Credit Note

#### User Stories

- Billing Reps create sales notes to apply special discount policies or rebates to a customer.
- When a billing rep is creating a note and they select the customer_id, the customer_rep_id present in the customer must be automatically added to the note.
- Notes can be automatically created from Void Sales Invoices by Sales Reps in another table. This Notes have product lines.
- Notes can be automatically created from Customer Returns by Logistic Reps in another table. This Notes have product lines.
- Billing Reps, Sales Reps, Logistic Reps or Managers can not update a credit note, only those archive=false can be deleted.
- Billing Reps use tables to filter and find notes by customer_id, customer_rep_id, total and balance.
- All Reps must be able to see the line items of each note, typically containing a product_id, amount, price and discount.
- All Notes are created in status=draft, an office manager must approve each of them by pressing a button.

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

##### Actions:

- Create
- delete
  - if archived!=true

# Debit Note

#### User Stories

- Billing Reps create sales notes to apply special discount policies or rebates to a customer.
- When a billing rep is creating a note and they select the customer_id, the customer_rep_id present in the customer must be automatically added to the note.
- Notes can be automatically created from Void Sales Invoices by Sales Reps in another table. This Notes have product lines.
- Notes can be automatically created from Customer Returns by Logistic Reps in another table. This Notes have product lines.
- Billing Reps, Sales Reps, Logistic Reps or Managers can not update a credit note, only those archive=false can be deleted.
- Billing Reps use tables to filter and find notes by customer_id, customer_rep_id, total and balance.
- All Reps must be able to see the line items of each note, typically containing a product_id, amount, price and discount.
- All Notes are created in status=draft, an office manager must approve each of them by pressing a button.

* Table

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

- Actions:
  - Create
  - delete
    - if archived!=true

# Sales_payment

#### User Stories

- Billing Reps create sales payments to record fisical and digital payments being received from customers.
- Remote Sales Reps create sales payments to record fisical and digital payments being received from customers.
- When a customer is selected, the customer's customer_rep_id is auto-selected
- When a customer is selected, the customer's pending sales invoices and notes with balance > 0 are displayed.
- The Billing/Remote Rep selects the invoices being paid and edit's it's amount if neccesary.
- The sales_payment total is updated each time the user add's invoices or edit's it's amount.
- When a Credit Note is selected, it's balance should be substracted from the total payment instead of aditioned.
- Reps can update and delete payments as long as archived=false.
- Details of items of the payment and their amounts should be stored in the field items_json
- Finance Reps approve payments and the backend system converts items_json into sales_payment_items among other steps.
- Reps and managers can search and filter using customer_id, created_at, applied_at,status,customer_rep_id,created_by_user_id,deposited_in_bank_id and total.
- Reps and managers can click on a row to open a dropdown with the items_json or sales_payment_items details.

- Table

  - number
  - readable_number
  - customer_id [R,F,C*]
  - created_at
  - applied_at
  - received_at
  - status
  - customer_rep_id [R,F]
  - created_by_user_id [R,F]
  - confirmed_by_user_id
  - deposited_in_bank_id [R,F,C*]
  - items_json
  - total [R,F]

* Create

  - on create set created_by_user_id to the current user
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

### User Cases

- When a mistake is made on a payment and that payment has alredy been archived, a billing rep can request the reversal of such payment.
- A finance rep will it turn approve the payment reveral
- Reps and managers can search and filter using customer_id, created_at, applied_at,status,customer_rep_id,created_by_user_id,deposited_in_bank_id and total.
- Reps and managers can click on a row to open a dropdown with the items_json or sales_payment_reversal_items details.

- Table

  - number [R,F]
  - readable_number
  - customer_id [R,F,C*]
  - created_at [R,F]
  - applied_at [R,F]
  - received_at
  - status [R,F]
  - customer_rep_id [R,F]
  - created_by_user_id [R,F]
  - confirmed_by_user_id [R,F]
  - deposited_in_bank_id [R,F]
  - items_json
  - total [R,F]

* Actions:

  - approve
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
