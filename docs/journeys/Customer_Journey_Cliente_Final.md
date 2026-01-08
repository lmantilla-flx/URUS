# Customer Journey: Cliente Final (Comprador)

## Perfil del Rol
* **Rol:** Cliente Final (Comprador).
* **Definición:** El paciente o consumidor que busca conveniencia, seguridad en la compra de sus productos y en el manejo de su receta y trazabilidad.
* **Foco:** Simplicidad y confianza en el manejo de salud.

---

## Matriz de Etapas y Acciones

| Etapa | Acciones | Punto de dolor - Emociones | Oportunidad / Valor | Dudas | MVP |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Onboarding Completo** | Registro y Validación KYC (A definir). | Validar si tienen algún dolor en el proceso actual. | Garantiza que el comprador es quien dice ser. | Revisar con Urus. Sugerencia Complif. | SI |
| **Onboarding Light** | Registro de email. | Validar si tienen algún dolor en el proceso actual. | Validación de email a través de OTP. Clientes que solo quieren realizar compras iniciales. | ¿Qué tipo de acciones realizará la persona que tiene este onboarding? | SI |
| **Carga de Receta x sistema** | Sube receta (OCR). | Error en la extracción de datos de la receta (monodroga -generico-, nombre comercial), por falla en la lectura del OCR. Recarga de la receta por error de OCR (recarga digital). | El sistema extrae automáticamente el medicamento y la composición (monodroga). Datos del médico y obra social/prepaga. | Hay que validar con zetti el producto, obra social, precio. ¿El stock se llevará con zetti? | SI |
| **Carga de Receta manual** | Sube datos de la receta de forma manual. | Tiempo en cargar los datos y posible reingreso de datos por errores. | Poder avanzar el pedido por sistema. | ¿Ya existe este proceso? ¿Cómo lo hacen? | SI |
| **Edición de Receta** | Valida los datos de la receta y edita en caso de que sean incorrectos. | Tiempo en cargar los datos y posible reingreso de datos por errores. | Garantiza que el comprador adquiera los medicamentos correctos de acuerdo a la receta. | | SI |
| **Selección de ubicación** | Elige farmacia cercana y visualiza precio/beneficio. | Que este no esté disponible en áreas cercanas a mi ubicación. | Transparencia en precio y los descuentos. | ¿Cómo se presentará la información de la farmacia, por precio según farmacia o algo estándar? | SI |
| **Reserva del medicamento** | La farmacia realiza la reserva del medicamento por X tiempo hasta que recibe el pago. | Se cancele la compra por falta de confirmación de pago. | Garantiza la disponibilidad del medicamento para el comprador. | ¿Cuánto tiempo tiene el comprador para pagar el producto? | SI |
| **Transacción** | Pago vía pasarela. | A definir. Medios de pagos reducidos. | Seguridad financiera. Permitir realizar pagos con mayor amplitud de medios de pagos. | ¿Mercado Pago? ¿Preguntar a nombre de qué entidad quedarían los pagos? ¿Urus o farmacia? | SI |
| **Confirmación de reserva** | Una vez se recibe la confirmación del pago, se envía notificación de plazo de entrega de la compra. | | Trazabilidad del proceso de compra. | ¿Existen métricas de entrega desde que se confirmó el pago? | SI |
| **Retiro medicamento** | Retiro de medicamento / producto en farmacia y entrega de receta física (si aplica). Presentación de documentación y validación de identidad. | Inconvenientes al retirar (fila, documentos faltantes), frustración si la receta física no cumple con los requisitos normativos u operativos. | Agilidad en el proceso de compra. | ¿Se puede hacer una devolución de la compra (dinero) ya que la receta no cumple con los requisitos mínimos? ¿Para la firma de la receta puede ir un menor de edad, tiene que ser el afiliado? Requerimientos mínimos para retirar un producto/medicamento según el tipo de producto. | SI |
| **Recepción de notificación** | Recibir las notificaciones configuradas por las farmacia. | | Sincronizados con el proceso de compras y novedades de los productos (dctos, campañas, etc). | | SI |
| **Seguimiento de la compra** | Desde la solicitud de la orden hasta la entrega. | | | | SI |