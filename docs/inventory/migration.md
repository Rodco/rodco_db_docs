# product <- producto

- Id <- id
- created_at <- created_at
- updated_at <- updated_at
- name <- name 
- product_cost_id <- costoHistoricoId
- product_brand_id <- select id from product_brand_id where name = marca
- product_type_category_id <- categoriaId 
- unit <- unidadMedida
- presentation <- presentacion
- code <- codigo
- description <- descripcion

# product_brand <- select marca from producto

- name <- marca

# product_type <- productoDepartamento

- id <- id
- name <- name

# product_type_category <- productoCategoria

- id <- id 
- name <- name 
- product_type_id <- productoDepartamentoId

# packing_list <- not migrate

# product_warehouse <- create SJ one

# product_warehouse_item <- producto

- id 
- product_warehouse_id <- SJ new
- product_id <- productId
- inventory <- inventario

#### shipping_route <- not migrate

#### product_price_list_customer

- id
- product_price_list_id
- customer_id
- created_at
- api_source

#### product_purchase <- movimientoInventario where tipo = 'co'
- id  
- created_at <- created_at
- updated_at <- updated_at
- status <- estado
- archived <- if estado = archivado ? true : false
- reference <- referencia

#### product_purchase_item <- movimientoInventario where tipo = 'co'

- product_id <- productoId
- amount <- cantidad
- cost <-  costo