### Product Price Selector

- Areas used:
  - creating and editing orders
  - creating and editing quotes

#### Overview

The components sits inline on create and edit forms. It's reponsible for letting the user select the products, prices and discounts of the order/quote and storing them as items_json.

#### Context

There are around 600 products on the system, prices are calculated using price lists specific for each customer. There could be 10 prices lists and each price list could have several variations.

Each product references an specific product_tax_id that contains the tax information for the product. This object could be loaded separaryl and cached locally since it does not change. New taxes may be introduced/updated from time to time so it's good refresh the cache often.

#### Details

Product Selection
Products are selected using the name of the product. The use types part of the name of the product and matching names are displayed. After the user selects the product, related variants should be displayed in the selection list.

Manual Price Selection
When the users changes the stock price/discount, the order/quote must be marked with the requires_office_approval boolean set to true. Min price is 1, min discount is 0, max discount is 99.

Setting Prices
When a product is selected, the component must calculate and use the lowest markup available for each price list. Also the product must use the discount in the product to calculate the final price. Price = Cost _ Markup + Cost _ Markup \* Discount.

Taxes
Each product has a product_tax referenced which contains the tax rate and code. Both information is needed to generate the order item.

Tax Exceptions
Some products are tax excempt. When that is the case, such exceptions must be included in the calculations for the totals for exceptions instead of taxed.

Tax Exonerations
Some customers can have goverment exonerations, the user should fill in the codes at the order/quote level. Exonerations are based on percetage deduction from the product tax rate [100%, 50%, 20%]. Tax totals should also be assigned on the exoneration totals instead of the taxed totals.

Examples

Regular Product

Except Product

Exonerated Product
