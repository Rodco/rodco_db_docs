#### Customer:

#### User Cases

- A sales rep creates a retail customer, retail customers have credit_term and credit_limit set to 0.
- A Billing Rep creates a wholesale customer that have credit_term and credit_limit.
- Reps use tables to filter and find customers by name, provice, customer_rep, customer_region, parent_corp,segment, credit_term and tags.

Table

- id [R,F]
- name [R,F,C*]
- identification [R,F,C*]
- province [R,F,C*] {San Jose, Heredia, Alajuela, Cartago, Puntarenas, Guanacaste, Limon}
- city [R,F,C*]
- gps_location [R,F,C]
- phone [R,F,C*]
- customer_rep_id [R,F,C*]
- customer_region_id [R,F,C*]
- customer_parent_corp_id
- customer_segment_id [R,F,C*]
- transport_id [R,F,C*]
- credit_term [R,F,C*] {0}
- credit_limit [R,F,C*] {0}
- comercial_name [R,F,C*]
- tags [R,F,C*]
- price_lists [R,F]

#### Customer_segment:

#### User Cases

- Sales Reps and managers can create customer_segments to be assigned to customers

Table

- id [R,F]
- name [R,F,C*]

#### Customer_region:

- id [R,F]
- name [R,F,C*]

#### User Cases

- Sales Reps and managers can create customer_segments to be assigned to regions

Table

- id [R,F]
- name [R,F,C*]

#### Customer_rep:

#### User Cases

- Managers can create customer_resp to be assigned to customers

Table

- id
- Name [R,F,C*]
- User_id [R,F,C*]
- Phone_number [R,F,C*]

#### Parent_corporation:

#### User Cases

- Managers can create parent_corporations to be assigned to customers

Table

- id
- name [R,F,C*]

#### Transport:

#### User Cases

- Logistics Reps can created and update transports to be included in customers/orders

Table

- id
- name [R,F,C*]
- description [R,C*]
