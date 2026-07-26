Markdown
# 📊 El Amigo Analytics - Business Intelligence & Data Engineering

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15%2B-blue?logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-Desktop-F2C94C?logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-Advanced_Queries-00758F?logo=sqlite&logoColor=white)
![ETL](https://img.shields.io/badge/Data_Quality_Score-98.9%25-success)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Visión General del Proyecto

**El Amigo Analytics** es una solución integral de **Business Intelligence, Ingeniería de Datos y Analítica Avanzada** desarrollada para **Ferretería El Amigo**[cite: 6]. El proyecto aborda la transformación digital end-to-end: desde la extracción y saneamiento (ETL) de datos transaccionales crudos provenientes de un sistema POS en Excel (~4,000 SKUs)[cite: 6], la construcción de un almacén de datos relacional normalizado en **PostgreSQL**[cite: 6], la ejecución de un *Playbook* de **25 consultas SQL estratégicas**[cite: 6], hasta la creación e implementación de un **Dashboard Ejecutivo Interactivo en Power BI**[cite: 6].

---

## 🎯 Desafíos del Negocio y Objetivos

### 🚨 Estado Pre-Analítico (Problema)
* **Silos de Información:** Registros dispersos en archivos locales de Excel con duplicados, inconsistencias de tipado y nulos[cite: 6].
* **Falta de Visibilidad en Inventario:** Compras empíricas sin cálculo de stock mínimo ni días de cobertura real, provocando quiebres de stock[cite: 6].
* **Fugas de Margen:** Descuentos descontrolados otorgados en mostrador por debajo del costo maestro[cite: 6].
* **Incertidumbre Comercial:** Desconocimiento de la cartera de clientes, tasa de abandono B2B/B2C y valor de vida del cliente (CLV)[cite: 6].

### 🎯 Estado Modernizado (Solución BI)
* **Centralización Relacional:** Data Warehouse analítico en PostgreSQL con un **Data Quality Score (DQS) del 98.9%**[cite: 6].
* **Automatización SQL:** Playbook de 25 consultas analíticas divididas en 5 capítulos estratégicos[cite: 6].
* **Toma de Decisiones Data-Driven:** Tablero ejecutivo dinámico en Power BI para el monitoreo continuo de KPIs financieros y operacionales[cite: 6].
* **Optimización del Capital de Trabajo:** Estimación de recuperación de **$12.5M en capital inmovilizado** y un incremento proyectado del **14.2% en utilidades netas**[cite: 6].

---

## 🏗️ Arquitectura de la Solución

El flujo de datos sigue un estándar moderno de Business Intelligence dividido en 4 capas principales[cite: 6]:

┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│  1. FUENTE POS  │ ───► │  2. MOTOR BD    │ ───► │ 3. CAPA SQL     │ ───► │ 4. POWER BI     │
│   Excel / CSV   │      │ PostgreSQL v15  │      │ 25 Queries      │      │  Dashboard      │
│  (Data Cruda)   │      │  (DQS: 98.9%)   │      │  Estratégicas   │      │   Ejecutivo     │
└─────────────────┘      └─────────────────┘      └─────────────────┘      └─────────────────┘


1. **Capa de Origen:** Extracción de datos transaccionales del sistema POS (Ventas, Compras, Productos, Clientes y Proveedores)[cite: 6].
2. **Capa de Almacenamiento & ETL:** Pipeline de limpieza, tipado de datos y carga en PostgreSQL garantizando integridad referencial (PK/FK) y B-Tree indexing[cite: 6].
3. **Capa Semántica & Analítica:** Desarrollo de consultas SQL avanzadas para agregaciones temporales, segmentación RFM, auditoría de márgenes y análisis de cobertura[cite: 6].
4. **Capa de Presentación:** Dashboard interactivo en Power BI con filtros dinámicos (Año, Mes, Vendedor, Subcategoría, Proveedor) y métricas DAX[cite: 6, 7].

---

## 📐 Modelo de Datos Relacional

El modelo dimensional sigue un esquema relacional optimizado en estrella/copo de nieve[cite: 6]:

* **Tablas de Hechos (Fact Tables):**
  * `ventas` (id_venta, id_cliente, codigo_producto, vendedor, fecha, cantidad, precio_venta_unitario, descuento, total_neto, utilidad, forma_pago)[cite: 6]
  * `compras` (id_compra, nit_proveedor, codigo_producto, fecha, costo_unitario, cantidad, total_compra)[cite: 6]
* **Tablas de Dimensión (Dimension Tables):**
  * `productos` (id_producto, sku, nombre_producto, marca, categoria, subcategoria, costo, precio, stock, stock_minimo, stock_maximo, estado)[cite: 6]
  * `clientes` (id_cliente, nombres, apellidos, numero_documento, ciudad, departamento, fecha_registro, segmento, estado)[cite: 6]
  * `proveedores` (nit_proveedor, razon_social, contacto, ciudad, categoria_principal)[cite: 6]

---

## 🔍 SQL Analytics Playbook (25 Consultas Estratégicas)

El repositorio incluye un conjunto de 25 consultas SQL divididas en 5 capítulos analíticos claves[cite: 6]:

### 1️⃣ Analítica de Ventas & Estacionalidad
* Evaluación de volumen mensual, picos de facturación (Marzo: $5.1M, Abril: $5.0M) y ticket promedio por vendedor[cite: 6].

### 2️⃣ Analítica de Clientes & Segmentación
* Aislamiento de **102 clientes inactivos** (>365 días sin comprar) y análisis de frecuencia por segmento (VIP, Mayorista, Minorista)[cite: 6].

### 3️⃣ Analítica de Inventarios & Cobertura
* Detección prioritaria de **33 SKUs en riesgo de quiebre de stock** por estar debajo del mínimo de seguridad y cuantificación de inventario dormido[cite: 6].

### 4️⃣ Analítica de Compras & Proveedores
* Auditoría de desviación entre costo pagado vs. costo maestro de lista y concentración de gasto por proveedor[cite: 6].

### 5️⃣ Analítica de Rentabilidad & Auditoría de Márgenes
* Identificación de ventas con margen crítico (<10%) o pérdida, y evaluación de ROI por forma de pago[cite: 6].

---

## 📈 Dashboard Ejecutivo Power BI

El cuadro de mando interactivo permite visualizar[cite: 6]:
* **KPIs Principales:** $43.38M Ingresos Totales | 42.43% Margen Bruto | $8,677 Ticket Promedio | 33 SKUs Bajo Mínimo | 102 Clientes en Riesgo[cite: 6].
* **Tendencia Temporal:** Evolución mensual de ventas y comportamiento estacional[cite: 6, 7].
* **Análisis Comercial:** Ranking de vendedores por facturación y top clientes VIP[cite: 6, 7].
* **Alertas Operativas:** Listado dinámico de productos urgentes por reabastecer[cite: 6, 7].

---

## 🛠️ Stack Tecnológico

| Tecnología | Categoría | Función en el Proyecto |
| :--- | :--- | :--- |
| **PostgreSQL v15** | Base de Datos Relacional | Almacenamiento centralizado, modelo relacional e integridad referencial[cite: 6]. |
| **SQL (ANSI)** | Lenguaje de Consulta | Desarrollo del Playbook de 25 consultas de negocio avanzadas[cite: 6]. |
| **Power BI Desktop** | Business Intelligence | Modelado dimensional, medidas DAX y tableros ejecutivos interactivos[cite: 6]. |
| **DBeaver / pgAdmin** | Gestor de Base de Datos | Entorno de desarrollo SQL y administración de servidor[cite: 6]. |
| **Git / GitHub** | Control de Versiones | Alojamiento y documentación del proyecto[cite: 6]. |

---

## 👤 Autor

**Yhon Jairo González Rivera**  
*Especialista en Business Intelligence & Data Analytics*  

* **LinkedIn:** [yhon-gonzalez-1692ba402](https://linkedin.com/in/yhon-gonzalez-1692ba402)
* **GitHub:** [@yhongo90](https://github.com/yhongo90)
* **Email:** yhonjairo90@hotmail.com
