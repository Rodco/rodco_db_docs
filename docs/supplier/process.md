# supplier:

# supplier_credit_note:

- on archived=true
  - set total_pending_payment = total

# suppler_debit_note:

- on archived=true
  - set total_pending_payment = total

# supplier_invoice:

- on archived=true
  - for each supplier_invoice_item : using product_warehouse_id create or update row with incoming inventory
  - Create new product_cost using incoming cost and FIFO cost formula with current cost, set supplier_invoice_id to product_cost
  - Update all product using old cost, with new cost.
  - set total_pending_payment = total

# supplier_invoice_item:
