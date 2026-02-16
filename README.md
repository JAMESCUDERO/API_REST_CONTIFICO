# Power BI Enterprise Dashboard – Integración API REST Contifico

 ## Resumen Ejecutivo
Este proyecto implementa una arquitectura de analítica empresarial en Power BI, integrando datos contables desde la API REST de Contifico.
La solución está diseñada bajo principios de automatización, seguridad, mantenibilidad y escalabilidad, orientada a entornos productivos.

## Objetivos Técnicos
Diseñar un pipeline de ingesta de datos vía API REST
Implementar autenticación segura basada en tokens
Normalizar y modelar datos semi-estructurados (JSON)
Aplicar modelado dimensional (Star Schema)
Optimizar rendimiento en Power BI Desktop y Service
Habilitar refresh automático y controlado

## Arquitectura de la Solución
Origen → Transformación → Modelo → Visualización
  ## Origen
    ✔ API REST de Contifico
    ✔ Endpoints desacoplados por entidad (ventas, clientes, inventario, documentos)
  ## Ingesta
    ✔Conectores Web en Power Query (M)
    ✔ Manejo de paginación y control de errores
    ✔ Parámetros para URL base y token
  ## Transformación
    ✔ Desanidado de estructuras JSON
    ✔ Tipado estricto de columnas
    ✔ Reglas de limpieza y estandarización
    ✔ Separación lógica de consultas: staging vs. final
  ## Modelo
    ✔ Modelo dimensional optimizado
    ✔ Relaciones unidireccionales
    ✔ Uso de tablas de dimensiones (Fecha, Cliente, Producto)
    ✔ Medidas centralizadas en DAX
  ## Visualización
    ✔ Dashboards orientados a toma de decisiones
    ✔ KPIs financieros y operativos
    ✔ Interacción controlada y diseño consistente

## Stack Tecnológico
Power BI Desktop & Service
Power Query (Lenguaje M)
DAX avanzado
API REST
JSON
Modelado Dimensional

Control de versiones en GitHub

Métricas y KPIs
Ingresos y variación porcentual
Documentos por estado
Evolución temporal de ventas
Análisis por cliente y producto
Indicadores de inventario (según endpoint)

## Buenas Prácticas Implementadas
✔ Separación de capas (ingesta / transformación / modelo)
✔ Queries reutilizables y parametrizadas
✔ Minimización de columnas y cardinalidad
✔ Uso exclusivo de medidas (no columnas calculadas innecesarias)
✔ Diseño preparado para incremental refresh
✔ Seguridad de credenciales fuera del código

## Seguridad y Gobierno
Tokens de autenticación excluidos del repositorio
Parámetros protegidos en Power BI
Diseño compatible con Row-Level Security (RLS)
Preparado para despliegue en entornos productivos

## Notas Finales
La solución puede extenderse fácilmente para:
Nuevos endpoints
Incremental refresh
Publicación en Power BI Service
Integración con gateways o dataflows
