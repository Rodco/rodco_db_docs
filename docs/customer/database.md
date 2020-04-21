#### Customer:

Retail and Wholesale customers

- id
- created_at
- update_at
- name [*]
- active {true}
- identification [*]
- province [*] {San José}
- state
- city
- Address
- gps_location
- phone
- email_for_invoice [*]
- customer_rep_id
- transport_id
- customer_region_id
- Customer_parent_corp_id
- customer_segment_id [*]
- credit_term [*] {0} (>=0)
- credit_limit [*] {0} (>=0)
- comercial_name
- billing_week_day
- tags
- price_lists
- balance
- expired_balance
- late_balance
- average_balance
- average_expired_balance
- average_late_balance
- percent_late_payments_3_months
- percent_expired_payments_3_months
- percent_ok_payments_3_months

  
#### Customer_segment:

Groups customers by segment

- id
- name [*]


#### Customer_region:

Groups customers by comercial region

- id
- name [*]


#### Customer_rep:

Representative that gets assign to customer

- id
- name [*]
- user_id [*]
- phone_number [*]

#### Transport:

Shipping Provider

- id
- name [*]
- description [*]



#### Parent_corporation:

Use in customers that belong to a larger commercial group and must be counted as a whole.

- id
- name [*]


#### Contact
* NOT DECIDED YET
- id
- name
- active
- identification
- email
- mobile
- address
- role
- description
- birthday
- tags
- is_owner
- brands
- bounce
- last_email_status
- last_email
- last_email_at
- customer_id
