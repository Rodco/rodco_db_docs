#### sales_credit_note -> documento where tipo = 'NC'

- Id <- id
- created_at <- created_at
- updated_at <- updated_at
- number <- consecutivo
- readable_number
- code <- clave
- archived <- status = archivado ? true : false
- credit_term <- plazo
- customer_id <- clienteId
- customer_rep_id  <- vendedorId>
- approved_by_billing_user_id <- approveBy
- approved_by_office_user_id 
- void_sales_credit_note_id
- replacement_sales_credit_note_id <- documentoAnuladorId
- pdf_url <- pdf
- xml_url <- xml
- xml_validation_url <- respuestaXml
- currency <- moneda
- exchange_rate <- tipoCambio
- service_sub_total_taxed <- totalServGravados
- service_sub_total_exempt <- totalServExcentos
- service_sub_total_exonerated <- totalServExonerado
- product_sub_total_taxed <- totalMercanciasGravadas
- product_sub_total_exempt <- totalMercanciaExcentas
- product_sub_total_exonerated <- totalMercExonerada
- sub_total_taxed <- totalGravado
- sub_total_exempt <- totalExcento
- sub_total_exonerated <- totalExonerado
- sub_total <- totalVenta
- discount_total <- totalDescuento
- sub_total_net <- totalVentaNeta
- tax_total <- totalImpuesto
- tax_total_returned <- totalIVADevuelto
- total <- totalComprobnate
- status <- estado 

#### sales_credit_note_item <- movimientoInventario where tipo = NC and documentoId = ^

- id <- id
- product_id <- productId
- price <- precio
- amount <- cantidad
- discount_rate <- descuento