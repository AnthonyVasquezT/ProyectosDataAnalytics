# Proyecto1DataAnalytics
En este repositorio estaré registrando los proyectos relacionados al análisis de datos y evidenciar mi aprendizaje.

## Descripción del proyecto
Este proyecto tiene como objetivo limpiar, transformar y analizar una base de datos de transacciones de ventas para convertirla en información útil para la toma de decisiones.  

El dataset contiene registros de facturación, productos, cantidades, fechas, precios, clientes y país. Durante la exploración inicial se identificaron problemas de calidad de datos como valores vacíos, descripciones inconsistentes, cantidades negativas, precios negativos o iguales a cero y registros sin identificación de cliente.

A partir de ello, realicé un proceso de depuración y estandarización en Power Query, seguido de un análisis en Power BI con indicadores clave y visualizaciones de negocio.

## Objetivos
- Identificar problemas de calidad de datos.
- Limpiar y estandarizar la información.
- Preparar una base confiable para análisis.
- Construir indicadores clave de negocio.
- Visualizar hallazgos relevantes en Power BI.

## Dataset utilizado
El proyecto se basó en un dataset de transacciones de retail con las siguientes columnas:

- `Invoice`
- `StockCode`
- `Description`
- `Quantity`
- `InvoiceDate`
- `Price`
- `Customer ID`
- `Country`

## Herramientas utilizadas
- Microsoft Excel
- Power Query
- Power BI
- GitHub

## Proceso de limpieza y transformación

### 1. Revisión inicial
Se realizó una inspección preliminar del archivo para identificar:
- tipos de datos incorrectos,
- valores nulos,
- textos con espacios o caracteres extraños,
- cantidades negativas,
- precios negativos o cero,
- registros sin identificación de cliente.

### 2. Estandarización de tipos de datos
Se verificó y ajustó el tipo de dato de cada columna:
- `Invoice` → texto
- `StockCode` → texto
- `Description` → texto
- `Quantity` → número entero
- `InvoiceDate` → fecha
- `Price` → número decimal
- `Customer ID` → número entero
- `Country` → texto

### 3. Limpieza de texto
Se aplicaron transformaciones de formato en las columnas de texto para:
- eliminar espacios innecesarios,
- limpiar caracteres invisibles,
- mejorar la consistencia de los valores.

### 4. Tratamiento de valores nulos
Se identificaron filas con:
- `Description` vacía,
- `Customer ID` vacío.

Dependiendo del objetivo del análisis, se decidió excluir registros que no aportaban valor al análisis principal.

### 5. Tratamiento de valores negativos y cero
Se identificaron valores negativos en `Quantity` y `Price`.  
Para evitar distorsiones en el análisis de ventas:
- se clasificaron los movimientos,
- se excluyeron registros con valores no válidos en el análisis principal,
- se conservó la trazabilidad del proceso de limpieza.

### 6. Anexado de consultas
Las dos bases del dataset fueron unidas en una sola consulta final para trabajar con una base consolidada y lista para análisis.

### 7. Creación de columnas calculadas
Se generó la columna:
- `TotalVenta` = `Quantity * Price`

Esta columna permitió calcular métricas de negocio y construir visualizaciones en Power BI.

## Análisis en Power BI

Se desarrolló un dashboard con los siguientes indicadores clave:

- **Ventas Totales**
- **Total de Transacciones**
- **Clientes Únicos**
- **Productos Únicos**

Además, se incluyeron visualizaciones para analizar:
- evolución de ventas,
- comportamiento por país,
- productos con mayor volumen de ventas,
- comportamiento general de la operación.

## Hallazgos y conclusiones
- Se identificaron registros con problemas de calidad de datos que podían afectar el análisis, por lo que fue necesario aplicar limpieza y validación antes de construir métricas.
- La depuración de vacíos, textos inconsistentes y valores negativos permitió construir una base más confiable para el análisis.
- La creación de `TotalVenta` facilitó la medición del rendimiento comercial.
- El dashboard permitió resumir la información de forma visual y rápida, mostrando los principales indicadores del negocio.
- Este proyecto demuestra una capacidad básica pero sólida para trabajar con datos reales, prepararlos para análisis y convertirlos en información útil para la toma de decisiones.

## Estructura del proyecto
```bash
.
├── data
│   ├── online_retail_II_raw
│   ├── online_retail_II_clean
├── powerbi
│   └── DashBoard_ProyectoAnlisisVentas.pbix
├── docs
│   └── README.md
└── screenshots
    ├── VisualizaciónGeneralDashboard.png
    ├── AplicacionFiltros.png
    ├── AplicacionFiltros2.png
    └── ProcesosRealizadosEnPoweQuery.png
