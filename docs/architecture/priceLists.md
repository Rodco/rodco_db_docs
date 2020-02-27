### Prices Lists

Prices lists defined the prices of standard products in orders and quotes. 

Product Prices can be standard using prices lists or manually defined by users. Anytime a prices is manually defined it requires a manager's approval.

Each product has a predefined and cosmetic discount. Product discounts do not modify the final markup, it just increases the price so that the discount is taken into consideration to reach the markup.


How are prices defined:
Prices are defined by markup from the cost. Discount are for marketing or cosmetic, they do not affect the markup but instead take into consideration the discount to achieve the desired markup. The discount is set at the product level and affects all price lists.

How is cost selected
Prices are not modified automatically when product cost changes. They are bound to the product_cost_for_price_id field in the product table. 

Primary Price Lists
This price list are meant for a large array of products, typically 100% of products for an specific market. They are assigned a Markup and discount the applies to all products.

Secondary Price Lists
This prices lists are meant to hold smaller amounts of products, categories that share a pricing strategy. It's done this way to simplify price lists managment and maintenance.

Price List Modifiers
Each price list can have modifiers, which are individual products that have a diferent markups than the price list they belong to. They are created individually.

Customer
Customer are initially assigned a base price list. They can also have serveral price lists asigned to them. The customer will always receive the lowest price from all the price lists.

