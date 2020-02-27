#### Customer:

Retail and Wholesale customers

- id
- created_at
- update_at
- name [*]
- active {true}
- identification [*]
- identification_type [*]
- province [*] {San José}
- state
- city
- Address
- gps_location
- phone
- email_for_invoice [*]
- email_for_sales
- email_for_billing
- customer_rep_id
- customer_region_id
- Customer_parent_corp_id
- customer_segment_id [*]
- credit_term [*] {0} (>=0)
- credit_limit [*] {0} (>=0)
- comercial_name
- shipping_supplier_id
- billing_week_day
- tags
- price_lists
- api_source [*]

#### Customer_segment:

Groups customers by segment

- id
- name [*]
- api_source [*]

#### Customer_region:

Groups customers by comercial region

- id
- name [*]
- api_source [*]

#### Customer_rep:

Representative that gets assign to customer

- id
- Name [*]
- User_id [*]
- Phone_number [*]
- api_source [*]

#### Parent_corporation:

Use in customers that belong to a larger commercial group and must be counted as a whole.

- id
- name [*]
- api_source [*]
