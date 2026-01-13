```mermaid
sequenceDiagram
    participant Cliente
    participant Plataforma_URUS
    participant Farmacia
    participant Sistema_de_Pagos

    Cliente->>Plataforma_URUS: Solicita compra
    Plataforma_URUS->>Farmacia: Nuevo pedido
    Farmacia->>Farmacia: Valida receta + cobertura + stock
    Farmacia-->>Plataforma_URUS: Confirma disponibilidad
    Plataforma_URUS-->>Cliente: Habilita pago
    Cliente->>Sistema_de_Pagos: Ejecuta pago
    Sistema_de_Pagos-->>Plataforma_URUS: Confirma transacción
    Sistema_de_Pagos-->>Plataforma_URUS: Error de pago
    Plataforma_URUS-->>Cliente: Ofrece reintentar
    Plataforma_URUS->>Farmacia: Habilita preparación una vez el pago está aprobado
    Farmacia->>Farmacia: Quema receta
    Farmacia->>Farmacia: Preparación del pedido
    Farmacia-->>Plataforma_URUS: Confirma preparado
    Plataforma_URUS-->>Cliente: Listo para retiro
    Cliente->>Farmacia: Retira en mostrador
    Farmacia-->>Cliente: Confirma entrega
```