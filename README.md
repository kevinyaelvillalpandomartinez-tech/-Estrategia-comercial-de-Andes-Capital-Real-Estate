# -Estrategia-comercial-de-Andes-Capital-Real-Estate
# 🏢 Proyecto de Análisis Comercial Inmobiliario — Grupo Andes

## 📌 Descripción del proyecto

Este proyecto analiza el desempeño comercial de una empresa inmobiliaria ficticia llamada **Grupo Andes**, con el objetivo de construir un dashboard ejecutivo que permita evaluar ventas, ingresos, clientes, propiedades, canales comerciales y recurrencia de clientes.

El análisis está orientado a responder preguntas clave de negocio como:

- ¿Cuánto ingreso total generó la empresa?
- ¿Cuántas propiedades se vendieron?
- ¿Cuál fue el ticket promedio de venta?
- ¿Qué tipo de propiedad genera más ingresos?
- ¿Qué canal de venta tiene mejor desempeño?
- ¿Qué ciudad concentra mayor volumen comercial?
- ¿Los clientes vuelven a comprar después de su primera adquisición?

---

## 🎯 Objetivo

Construir un análisis comercial inmobiliario que ayude a la toma de decisiones estratégicas mediante:

- Limpieza y validación de datos.
- Modelado de datos bajo esquema estrella.
- Creación de medidas de negocio.
- Análisis temporal con métricas YTD, MTD y YoY.
- Análisis de cohortes para evaluar recurrencia de clientes.
- Diseño de un dashboard ejecutivo en Power BI o Tableau.

---

## 📂 Datasets utilizados

El proyecto se basa en un modelo de datos compuesto por las siguientes tablas:

### `hecho_ventas_propiedades`
Tabla principal de hechos con las transacciones de venta.

Contiene información como:

- Fecha de venta
- Cliente
- Propiedad
- Precio de venta
- Canal de venta
- Porcentaje de comisión

### `dim_clientes`
Tabla dimensional con información de los clientes.

Incluye variables relacionadas con segmentación y comportamiento del cliente.

### `dim_propiedades`
Tabla dimensional con características de las propiedades.

Incluye información como:

- Tipo de propiedad
- Ciudad
- Ubicación
- Tamaño
- Características comerciales

### `dim_fecha`
Tabla calendario creada para el análisis temporal.

Incluye:

- Año
- Mes
- Número de mes
- Año-Mes

---

## 🧹 Limpieza y preparación de datos

Durante la preparación de datos se realizaron las siguientes validaciones:

- Conversión de `fecha_venta` a formato fecha.
- Validación de campos numéricos.
- Conversión de `porcentaje_comision` a formato porcentaje.
- Revisión de duplicados en claves primarias.
- Validación de relaciones entre tablas.
- Revisión de consistencia para el modelado del dashboard.

> Oportunidad de mejora detectada: documentar con mayor detalle la revisión de valores nulos y justificar si fueron eliminados, corregidos o conservados.

---

## 🧩 Modelado de datos

El modelo fue estructurado como un **esquema estrella**, usando la tabla de ventas como tabla central y conectándola con tablas dimensionales.

### Estructura del modelo

- `hecho_ventas_propiedades` como tabla de hechos.
- `dim_clientes` conectada por clave de cliente.
- `dim_propiedades` conectada por clave de propiedad.
- `dim_fecha` conectada por fecha de venta.

### Reglas del modelo

- Relaciones uno a muchos `1:*`.
- Dirección de filtro simple.
- Relaciones activas.
- Claves correctamente relacionadas.

---

## 📊 Medidas principales

Se construyeron métricas para evaluar el desempeño comercial del negocio.

### KPIs base

- **Ingreso Total**
- **Cantidad de Ventas**
- **Ticket Promedio**
- **Comisión Total**

### Medidas de participación

Estas medidas permiten analizar qué proporción del ingreso total aporta cada categoría:

- Participación de ingresos por tipo de propiedad.
- Participación de ingresos por canal de venta.
- Participación de ingresos por segmento de cliente.

### Inteligencia de tiempo

Se trabajaron métricas para analizar evolución temporal:

- Ventas Year to Date — YTD.
- Ventas Month to Date — MTD.
- Ventas del año anterior.
- Crecimiento Year over Year — YoY.

> Oportunidad de mejora detectada: revisar el formato del indicador YoY para asegurar que se interprete correctamente como porcentaje.

---

## 📈 Estructura del dashboard

El reporte se diseñó con tres vistas principales.

### 1. Overview Ejecutivo

Vista enfocada en el desempeño general del negocio.

Incluye:

- Ingreso total.
- Cantidad de ventas.
- Ticket promedio.
- Comisión total.
- Tendencia de ventas en el tiempo.
- Ingresos por ciudad.
- Crecimiento YoY.

### 2. Análisis Comercial

Vista enfocada en identificar los principales motores de ingreso.

Incluye:

- Ingreso por tipo de propiedad.
- Ingresos por canal de venta.
- Ingresos por segmento de cliente.
- Tabla con formato condicional tipo semáforo.
- Tooltips con medidas de participación porcentual.

### 3. Análisis de Cohortes

Vista enfocada en medir recurrencia de clientes.

Incluye:

- Matriz de cohortes.
- Mes de cohorte.
- Mes de venta.
- Ingreso o cantidad de ventas por cohorte.
- Comparación del comportamiento de recompra entre grupos de clientes.

> Oportunidad de mejora detectada: ajustar la definición de `Mes Venta` si se desea representar el mes calendario real de la transacción y no solo el desfase mensual desde la primera compra.

---

## 🔎 Hallazgos principales

- El periodo analizado generó aproximadamente **$6,012 millones** en ingresos.
- Se registraron cerca de **9 mil transacciones inmobiliarias**.
- Las **casas** fueron el tipo de propiedad con mayor contribución al revenue.
- **Ciudad de México** concentró el mayor volumen de operaciones.
- El canal **Corredor** fue el canal con mayor generación de ingresos.
- Las cohortes captadas durante el primer cuatrimestre de 2023 mostraron mayor recurrencia.
- El negocio presentó un crecimiento YoY moderado, cercano al **1.11%**, sujeto a validación del formato del indicador.

---

## 💡 Insights accionables

- Las casas representan el principal motor comercial, por lo que conviene priorizar campañas, inventario y esfuerzos comerciales hacia esta categoría.
- El canal Corredor muestra un desempeño superior y puede servir como referencia para optimizar otros canales de venta.
- Las cohortes del primer cuatrimestre de 2023 presentan mejor recurrencia, lo que sugiere revisar qué estrategias de adquisición y seguimiento se usaron en ese periodo.
- La concentración de ventas en una ciudad y un canal específico representa una fortaleza, pero también un posible riesgo de dependencia comercial.
- Incrementar la retención puede elevar el valor de vida del cliente y mejorar los ingresos futuros.

---

## ✅ Recomendaciones estratégicas

- Priorizar la comercialización de casas por su alta contribución al ingreso.
- Fortalecer el canal Corredor e identificar sus mejores prácticas.
- Replicar las estrategias de captación usadas en las cohortes con mayor recurrencia.
- Implementar programas de seguimiento postventa para aumentar recompra y fidelización.
- Diversificar los canales de venta para reducir dependencia comercial.
- Expandir oportunidades en ciudades con menor participación, pero potencial de crecimiento.
- Revisar y validar el cálculo de crecimiento YoY antes de usarlo como indicador ejecutivo final.

---

## 🛠️ Herramientas utilizadas

- **Power BI** para modelado, medidas DAX y dashboard.
- **DAX** para medidas de negocio, inteligencia de tiempo y cálculos de participación.
- **Modelo estrella** para estructurar relaciones entre tablas.
- **Análisis de cohortes** para evaluar recurrencia.
- **Visualización de datos** para comunicar hallazgos ejecutivos.

---

## 📌 Evaluación del proyecto

El proyecto obtuvo una evaluación final de:

## **92 / 100 puntos**

### Fortalezas identificadas

- Buena estructura del dashboard.
- KPIs bien seleccionados.
- Modelo de datos correctamente planteado.
- Uso adecuado de medidas base y medidas de participación.
- Visualizaciones alineadas con preguntas de negocio.
- Recomendaciones estratégicas conectadas con los hallazgos.

### Áreas de mejora

- Documentar mejor la revisión de valores nulos.
- Revisar el formato del crecimiento YoY.
- Afinar el campo utilizado para el análisis de cohortes.
- Cerrar placeholders o frases incompletas dentro del resumen ejecutivo.

---

## 🚀 Conclusión

Este proyecto demuestra la capacidad de transformar datos inmobiliarios en información útil para la toma de decisiones comerciales.

A través del dashboard, Grupo Andes puede identificar sus principales fuentes de ingreso, evaluar la evolución de ventas, detectar patrones de recurrencia en clientes y tomar decisiones estratégicas enfocadas en crecimiento, rentabilidad y retención.

---

## 👤 Autor

**Kevin Yael Villalpando Martínez**  
Data Analyst Jr. | Power BI • SQL • Python 
