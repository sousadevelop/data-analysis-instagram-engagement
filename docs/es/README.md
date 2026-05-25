# Análisis de engagement en Instagram

## Visión general

Este proyecto organiza un análisis exploratorio del engagement en Instagram de una empresa. La documentación se basa en los notebooks existentes y mantiene sin cambios las conclusiones analíticas.

Fuentes analíticas originales:

- `data-analysis-instagram-engagement-part01.ipynb`
- `data-analysis-instagram-engagement-part02.ipynb`
- `08. Analisando o engajamento no Instagram.xlsx`

## Contexto del problema

La pregunta central de los notebooks es:

> ¿Qué tipo de contenido genera más engagement en el Instagram de la empresa?

Las indicaciones originales son ignorar la columna `Visualizações`, enfocarse en likes, comentarios e interacciones, y tratar las tags vacías como publicaciones sin tag.

## Metodología

El análisis está dividido en dos notebooks:

- Un análisis general por tipo de contenido, presencia de personas, campañas y carrusel.
- Un análisis enfocado en tags usando `split` y `explode` para evaluar tags combinadas por separado.

Las principales etapas incluyen importar el archivo Excel con pandas, tratar valores nulos en carrusel, revisar estadísticas descriptivas, graficar likes y comentarios a lo largo del tiempo, ordenar publicaciones por likes y agrupar métricas con `groupby`.

## Principales insights

Los insights siguientes provienen de los notebooks existentes:

- Las publicaciones con personas tienen mucho más engagement para esta marca.
- Las publicaciones de campaña también presentan mejor desempeño.
- En este dataset, el carrusel no fue un factor diferencial para mejorar el engagement.
- Las promociones tuvieron el mayor engagement promedio en el análisis por tags.
- Las fechas conmemorativas y trends también mostraron buen engagement.
- Los videos sin personas tuvieron bajo desempeño, mientras que videos con personas, trends o fechas conmemorativas tuvieron mejores resultados.
- La tag `Loja` no debe juzgarse como mala hasta probarla con personas o campañas.
- Se recomienda continuar el monitoreo porque la base aún contiene poca información.

Resultados numéricos seleccionados ya presentes en los outputs de los notebooks:

- Likes promedio con personas: `14.664,55`.
- Likes promedio sin personas: `4.256,67`.
- Likes promedio con campañas: `18.173,27`.
- Likes promedio sin campañas: `7.928,33`.
- Likes promedio de la tag `Promoções`: `27.458,33`.
- Likes promedio de la tag `Datas comemorativas`: `20.752,25`.
- Likes promedio de la tag `Trends`: `20.024,00`.

## Limitaciones

- El análisis es exploratorio y se basa solo en el historial disponible.
- El dataset tiene un número limitado de publicaciones.
- Algunas combinaciones de formato, personas y campañas tienen pocas observaciones.
- Después de usar `explode` en tags, el propio notebook recomienda usar esos datos transformados solo para análisis relacionados con tags.
- Las promociones pueden implicar costos que no se evalúan en las métricas actuales.
- El análisis identifica patrones observados, no efectos causales.

## Próximos pasos

- Continuar monitoreando nuevas publicaciones.
- Probar la tag `Loja` con personas o campañas.
- Evaluar costo y retorno de campañas promocionales.
- Exportar figuras a `reports/figures/` solo cuando se generen desde el análisis existente.
- En una tarea futura, estandarizar rutas de notebooks hacia `data/raw/` sin cambiar conclusiones analíticas.

## Estructura del proyecto

Consulta [data/README.md](../../data/README.md) para la gestión de datos y [reports/final_report.md](../../reports/final_report.md) para el informe consolidado.

## Ejecución local

```bash
pip install -r requirements.txt
jupyter notebook
```

Ejecuta los notebooks desde la raíz del repositorio para preservar la ruta actual del archivo Excel.
