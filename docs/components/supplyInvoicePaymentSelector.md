### Sales Invoice Payment Selector

#### used in

#### Context

There are supplier invoice and notes as well as expense invoices and notes with balances. We use supplier_payment in order to record payments.

Each document is recorded in the supplier_payment_item with the amount that's being payed. A supplier_payment can have one or more sales_payment_item.

This components display all the pending invoices, credit and debit notes as well as expense invoices and notes for the selected supplier and enables the user to enter the amount being paid.

#### Requirements

Invoices and Notes array of id's, type and payment amounts should be stored in items_json.

Invoices and Notes should have numeric inputs that when click display the full amount and are editable down to 0.

Invoices and Notes with 0 value as it input should not be sent as part of the payload, or stored.

Credit and Debit notes should appear in a separate section or be somehow diferentiated so there are no confusions.

Each time an input is changed, the total of supplier_payment must be updated.
