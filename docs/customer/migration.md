#### Customer <- cliente

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

- id <- id 
- name <- name

#### Customer_region <- zona

- id <- id
- name <- name

#### Customer_rep <- vendedor

- id <- id 
- name <- name
- user_id <- usuarioId

#### Parent_corporation <- clienteGrupoComercial
 
- id <- id
- name <- name 

#### Contact
- id <- id
- name <- name
- active <- activo
- identification <- cedula
- email <- email
- mobile <- mobile
- address <- direccion
- role <- rol
- description <- descripcion
- birthday <- fechaNacimiento
- tags <- tags
- is_owner <- propietario
- brands <- marcas
- bounce <- bounce
- last_email_status <- esteadoUltimoEmail
- last_email <- ultimoEmail
- last_email_at <- fechaUltimoEmail
- customer_id <- clienteId
