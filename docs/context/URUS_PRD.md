# Product Requirements Document (PRD): URUS Farma

## 1. Visión del Producto y Roadmap
* **Producto:** Urus Farma Web App (PWA).
* **Cliente:** Digital Health Unit S.R.L. (DHU).
* **Tech Stack:** React (PWA), Java Spring Boot (Microservicios Plug), AWS EKS.

### Objetivos Principales
1.  **Digitalizar el flujo de compra:** Transformar el proceso tradicional de adquisición de medicamentos con receta en un flujo digital completo.
2.  **Conectar el ecosistema:** Integrar usuario final, farmacias, médicos y logística.
3.  **Seguridad y Cumplimiento:** Implementar KYC (RENAPER) y asegurar la "quema" de recetas oficiales.
4.  **Transacciones Seguras:** Integración con Mercado Pago o similares.

### Roadmap de Fases
* **Fase 1: Discovery (2 Semanas):** UX/UI y arquitectura detallada.
* **Fase 2: Release 1 - MVP (16 Semanas):** Foco en Retiro en Farmacia. Incluye KYC, OCR, API Zetti y pago online.
* **Fase 3: Release 2 - Incremento (6 Semanas):** Envío a Domicilio (API Toque) y recetas digitales (API Dctor).

---

## 2. KPIs de Negocio y Producto

### KPIs de Negocio
| KPI | Objetivo (Target MVP) | Racional |
| :--- | :--- | :--- |
| Cuota de Farmacias Activas | > 5% (Pilotaje) | Penetración inicial. |
| GMV (Gross Merchandise Value) | (Confidencial) | Desglose Venta Libre vs. Bajo Receta. |
| Tasa de Conversión (Upsell) | > 15% | Captura de compra adicional al retirar. |
| Ticket Promedio | > AR$ 7,500 | Ajustado por inflación e-commerce 2024/25. |

### KPIs de Producto (UX)
| KPI | Objetivo (Target MVP) | Racional |
| :--- | :--- | :--- |
| Tasa de Éxito de OCR | > 80% | Evitar abandono por errores de carga. |
| Tiempo de "Click-to-Ready" | < 2 Horas | Valor de "ahorrar fila". |
| Tasa de Rechazo de Recetas | < 10% | Calidad de instrucciones de captura fotográfica. |
| Tasa de Éxito en Carga | > 65% | Punto de dolor más crítico. |
| Abandono de Checkout | < 20% | Monitoreo de pasarela de pagos. |

### KPIs de Eficiencia Operativa (Farmacia)
| KPI | Objetivo (Target MVP) | Racional |
| :--- | :--- | :--- |
| Tiempo de "Pick & Pack" | < 45 min | Clave para el MVP de retiro en tienda. |
| Tasa de Cancelación (Stockout) | < 2% | Discrepancia API Zetti vs. estantería física. |
| Active Pharmacies Rate | > 80% | Detección de farmacias "zombies". |

---

## 3. Arquitectura y Decisiones Técnicas

| Decisión | Justificación | Beneficio |
| :--- | :--- | :--- |
| **Microservicios + SAGA** | Flujo complejo con múltiples sistemas independientes. | Resiliencia (acciones compensatorias) y escalabilidad selectiva. |
| **Kubernetes (AWS EKS)** | Necesidad de plataforma elástica y autogestionada. | Alta Disponibilidad y escalabilidad automática ante picos. |
| **Frontend PWA (React)** | Accesibilidad móvil sin descarga de tiendas. | Experiencia superior y capacidades offline básicas. |
| **Aislamiento de Partners** | Dependencia crítica de APIs externas (Zetti, Toque, etc.). | Flexibilidad para cambiar partners sin afectar el core. |

---

## 4. Historias de Usuario Priorizadas (MVP)

### Historia 1: Onboarding y Validación de Identidad (KYC)
* **Prioridad:** Bloqueante.
* **Como** nuevo usuario de Urus Farma, **quiero** registrarme y validar mi identidad biométrica o documental, **para** poder realizar compras de medicamentos regulados de forma legal y segura.
* **KPI:** Costo de Adquisición de Cliente Validado (CACv) < AR$ 3.000.

### Historia 2: Carga de Receta con OCR
* **Prioridad:** Alta.
* **Como** paciente con una receta física, **quiero** subir una foto de la receta y que el sistema detecte los medicamentos, **para** agilizar la búsqueda y evitar escribir nombres complejos de drogas.
* **KPI:** Tasa de Éxito de OCR > 80%.

---

## 5. Modelo de Soporte y Niveles de Servicio (SLA)

| Severidad | Descripción | SLA Respuesta | Objetivo Resolución |
| :--- | :--- | :--- | :--- |
| **Crítico (S1)** | Caída total del servicio core. Sin workaround. | 8 horas corridas. | 12 horas corridas. |
| **Alto (S2)** | Funcionalidad principal degradada. Afecta > 20% usuarios. | 12 horas corridas. | 24 horas hábiles. |
| **Medio (S3)** | Fallo no crítico con workaround viable. | 16 horas hábiles. | 5 días hábiles. |
| **Bajo (S4)** | Consultas, problemas cosméticos o dudas. | 24 horas hábiles. | Plazo razonable. |