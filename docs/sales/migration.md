#### electronic_document_log <- registroElectronico

- id <- id
- document_id <- documentoId
- type <- tipo
- code <- clave
- status <- estado
- response <- respuesta

#### product_price_list:

- id
- name
- markup

#### product_price_list_item:

- id
- product_id
- markup 
- price_type
- product_price_list_id

#### quote <- orden where tipo = proforma

- id 
- created_at <- created_at
- updated_at <- updated_at
- customer_id <- clienteId
- status <- estado 
- customer_rep_id <- vendedorId
- customer_order_number <- name
- credit_term <- plazo
- currency <- moneda
- exchange_rate <- tipoCambio
- shipping_date <- fechaEntrega
- order_id <- id
- total <- total
- requires_office_approval <- especial
- approved_by_office_user_id <- approveBy
- approved_by_office_at <- fechaAprobacion
- description <- descripcion
- origin <- fuente

#### order:

- id <- id
- created_at <- created_at
- updated_at <- updated_at
- customer_id <- clienteId
- status <- estado 
- customer_rep_id <- vendedorId
- customer_order_number <- name
- approved_by_office_user_id <- approveBy
- approved_by_office_at <- fechaAprobacion
- credit_term <- plazo
- currency <- moneda
- exchange_rate <- tipoCambio
- shipping_date <- fechaEntrega
- sales_invoce_id <- documentoId
- total <- total 
- requires_office_approval <- especial
- description <- descripcion
- origin <- fuente
- archived <- if estado == 'archivado' ? true : false