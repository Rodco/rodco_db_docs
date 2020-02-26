### Sales Invoice Payment Selector

#### used in

#### Context

There are sales invoice and notes with balances. We use sales_payment in order to record payments. Each document is recorded in the sales_payment_item with the amount that's being payed. A sales_payment can have one or more sales_payment_item.

This components display all the pending invoices, credit and debit notes for the selected customer and enables the user to enter the amount being paid.

#### Requirements

Invoices and Notes array of id's and payment amounts should be stored in items_json.

Invoices and Notes should have numeric inputs that when click display the full amount and are editable down to 0.

Invoices and Notes with 0 value as it input should not be sent as part of the payload, or stored.

Credit and Debit notes should appear in a separate section or be somehow diferentiated so there are no confusions.

Each time an input is changed, the total of sales_payment must be updated.
