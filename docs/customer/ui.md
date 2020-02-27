#### Customer:

Retail and Wholesale customers

Table

- id [R,F]
- name [R,F,C*]
- identification [R,F,C*]
- identification_type [R,F,C*] {Fisica, Juridica, Dimex, Extranjero}
- province [R,F,C*] {San Jose, Heredia, Alajuela, Cartago, Puntarenas, Guanacaste, Limon}
- city [R,F,C*]
- gps_location [R,F,C]
- phone [R,F,C*]
- customer_rep_id [R,F,C*]
- customer_region_id [R,F,C*]
- customer_parent_corp_id
- customer_segment_id [R,F,C*]
- credit_term [R,F,C*] {0}
- credit_limit [R,F,C*] {0}
- comercial_name [R,F,C*]
- tags [R,F,C*]
- product_price_list_id [R,F,C*] {1}
- price_lists [R,F]

#### Customer_segment:

Table

- id [R,F]
- name [R,F,C*]

#### Customer_region:

Table

- id [R,F]
- name [R,F,C*]

#### Customer_rep:

Table

- id
- Name [R,F,C*]
- User_id [R,F,C*]
- Phone_number [R,F,C*]

#### Parent_corporation:

Table

- id
- name [R,F,C*]
