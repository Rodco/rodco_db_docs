#### Customer <- cliente

Retail and Wholesale customers

- id <- id
- created_at <- created_at
- update_at <- updated_at 
- name <- name
- active <- activo
- identification <- cedula
- identification_type <- tipoCedula
- Address <- direccion
- gps_location <- posicionGPS
- phone <- telefono
- email_for_invoice <- correoDocumentosElectronicos
- customer_rep_id <- vendedorId
- customer_region_id <- zonaId
- Customer_parent_corp_id
- customer_segment_id <- segmentoId
- credit_term <- plazoPago
- credit_limit <- creditoLimite
- comercial_name <-nombreComercial
- billing_week_day <- cobroDia
- tags <- tags

#### Customer_segment <- segmento

Groups customers by segment

- id <- id 
- name <- name

#### Customer_region <- zona

Groups customers by comercial region

- id <- id
- name <- name

#### Customer_rep <- vendedor

Representative that gets assign to customer

- id <- id 
- Name <- name
- User_id <- usuarioId

#### Parent_corporation <- clienteGrupoComercial

Use in customers that belong to a larger commercial group and must be counted as a whole.
 
- id <- id
- name <- name 
