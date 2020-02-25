# Sales Invoice

Sales invoices should dropdown and display in accordion the list of sales_invoice_items.

Sales_Invoice_Items should have checkboxes or numeric inputs used to insert the amount of items to be returned. Max value of input should be the amount of sales_invoice_items.

- Actions
  - Resend
    - send sales_invoice_id to /sales_invoice/resend
  - Return
    - send sales_invoice_items id's and amounts to /sales_invoice/return

# Order

- Actions

  - Approve
    - send order id to order/approve
  - Duplicate
    - send order id to order/duplicate
