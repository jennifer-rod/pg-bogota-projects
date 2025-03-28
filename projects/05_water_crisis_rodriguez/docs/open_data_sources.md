# Fuentes de Datos Abiertos para el Sistema de Monitoreo Hídrico de Bogotá

A continuación se presenta una tabla estructurada con información sobre fuentes de datos abiertos relevantes para el desarrollo de un Sistema de Monitoreo Hídrico para Bogotá, que permitirá integrar mediciones de embalses, consumo por zona y red de acueducto en una base de datos PostgreSQL.

| Ciudad/Región | Fuente de Datos | URL de Acceso | Tipo de Datos | Categoría | Frecuencia de Actualización | Formato |
|---------------|-----------------|---------------|---------------|-----------|----------------------------|---------|
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/dato-abierto-suscriptores-2024-2 | Cantidad de suscriptores del servicio de acueducto y alcantarillado por localidad y estrato | Recursos hídricos, Demografía | Trimestral | CSV |
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/dato-abierto-consumo-promedio-2024-2 | Consumo promedio de agua potable por suscriptor facturado en Bogotá, Soacha y Gachancipá | Recursos hídricos, Consumo | Mensual | CSV |
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/cobertura-bogota-2024-2 | Cobertura residencial de acueducto de Bogotá, incluyendo predios en proceso de legalización | Recursos hídricos, Infraestructura | Mensual | CSV |
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/conduccion-acueducto-bogota-d-c | Red de transporte de agua potable desde la Planta de Tratamiento hasta los tanques de almacenamiento | Recursos hídricos, Infraestructura | No especificada | Esri REST, GPKG, GeoJSON, SHP, KML, DXF |
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/racionamiento-de-agua-bogota-d-c | Zonas de restricción con suspensiones alternadas de agua debido al bajo nivel de los embalses | Recursos hídricos, Gestión de crisis | Según necesidad | Esri REST, GPKG, GeoJSON, SHP, KML, DXF |
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/indice-de-continuidad-2022 | Continuidad del Servicio de acueducto por Área Prestadora de Servicio (APS) | Recursos hídricos, Calidad del servicio | Anual | CSV |
| Bogotá, Colombia | Empresa de Acueducto y Alcantarillado de Bogotá | https://datosabiertos.bogota.gov.co/dataset/dato-abierto-irca-julio-diciembre-2023 | Índice de Riesgo de la Calidad del Agua para Consumo Humano | Recursos hídricos, Salud pública | Semestral | CSV |
| Bogotá, Colombia | Personería de Bogotá | https://www.personeriabogota.gov.co/sala-de-prensa/notas-de-prensa/item/1288-preocupa-tasa-constante-de-descenso-de-niveles-de-los-embalses-del-sistema-chingaza | Monitoreo satelital de niveles de los embalses del sistema Chingaza (Chuza y San Rafael) | Recursos hídricos, Monitoreo | Mensual | No especificado |
| Bogotá, Colombia | Secretaría Distrital de Ambiente | https://datosabiertos.bogota.gov.co/ | Información sobre aguas subterráneas y 521 pozos de agua subterránea en Bogotá | Recursos hídricos, Geología | No especificada | No especificado |

## Detalles de las Fuentes de Datos

Los datos proporcionados por la Empresa de Acueducto y Alcantarillado de Bogotá (EAAB) ofrecen una base sólida para el desarrollo del Sistema de Monitoreo Hídrico. Esta información incluye aspectos críticos como el consumo de agua por zonas, la cobertura del servicio, y datos geoespaciales sobre la red de acueducto[4].

La Personería de Bogotá proporciona monitoreo continuo de los embalses principales que abastecen a la ciudad, permitiendo hacer seguimiento a las tasas de descenso de volumen en Chuza y San Rafael, elementos esenciales para predecir posibles déficits hídricos[2].

Complementariamente, la Secretaría Distrital de Ambiente ofrece información sobre aguas subterráneas, lo que añade una capa importante de datos para comprender completamente el ciclo del agua en la ciudad y buscar fuentes alternativas en caso de escasez[3].

## Consideraciones para el Proyecto

Para la implementación efectiva del sistema en PostgreSQL, se recomienda:

1. Aprovechar los formatos geoespaciales disponibles (Shapefile, GeoJSON) para implementar extensiones PostGIS
2. Establecer procesos ETL automatizados considerando las diferentes frecuencias de actualización
3. Diseñar un modelo de datos que permita relacionar los niveles de embalses con patrones de consumo por zona
4. Implementar un sistema de alertas basado en umbrales de volumen de los embalses y tendencias de consumo

Estas fuentes de datos cumplen con los requisitos de ser oficiales y específicas para el proyecto de monitoreo hídrico, permitiendo construir un sistema robusto para la predicción de déficits y la priorización de intervenciones[1][4].

Citations:
[1] https://www.acueducto.com.co/wps/vanityurl/datos_abiertos
[2] https://www.personeriabogota.gov.co/sala-de-prensa/notas-de-prensa/item/1288-preocupa-tasa-constante-de-descenso-de-niveles-de-los-embalses-del-sistema-chingaza
[3] https://www.ambientebogota.gov.co/noticias-de-ambiente?p_p_id=101&p_p_lifecycle=0&p_p_state=maximized&_101_struts_action=%2Fasset_publisher%2Fview_content&_101_assetEntryId=1268250&_101_type=content&_101_urlTitle=secretaria-de-ambiente-le-cuenta-a-la-ciudadania-todo-lo-que-debe-saber-sobre-el-agua-subterranea-en-bogota
[4] https://datosabiertos.bogota.gov.co/organization/eaab
[5] https://www.acueducto.com.co/wpsportal/wps/portal/EAB2/Home/transparencia_informacion_publica/datos_abiertos/datos-abiertos/!ut/p/z1/xVhNd6JKEP0rzCK7YSiaj26WiIhRiaIwSdzkNNAm5CASwMzLv39N4rwMmqDvGM7ookGrbt2qriqqkZbSjbTM6HNyT6tkk9GU398u9Tvds0AmgK4AFB08zzJ9a3ylEF-Trl8FoPExoTdHPQXAmSJpyf8eEx0NHcL1r3QEOtEGHkK2DDb-UP9PpGP6P6WltMyjJJZuIwSxQkNV1I0VEVWkU5EYeiTimOmMYhkTptXSUVbl1YN0m2-KiqZZcRdtsopl1R0rL2BbbmmRbC6gKmhW5rRgWZTQC8A_hJhWm1KgYcIKflEjldWO_38EnalKwLP7l-7CHoCpvvn_Hj8VWeAtZr35NLCGI0A7_RaBpv-mYYE-dfqDuXolw0-1Xd-fwzn25ZmsnqbfQrChT2S_D5459B3dMS57GPbtHwq06Os9bV_fGbgGeLrpTTWVs52gs-zXBhrxJ96ix_PP8ybjuczh5SPxs9Bp_FsMnFQ_LQLLU-q3RWDZXp6jJkFnMMA8_-f2cGz3EAyUuoMkj09PS5MXXl1n_1TSTXvlpVRg67xgJS-7lL0IMRMaxSi8CDSKWLkRqMBlk2y1KdY04g1LyLdhmkRcrwYuNqmwibZpxTFjtmJZSYXHbZxwiPQCioSV97yeOXrOijiJaXngTKOYYST_JWdiFhWs7j3v3ux-QCDjmhQqXMu9542QVg9ijSHdNGVaPavb1McgnDF7Rfhbrr8R-O33H3Su6_7byFyia-AhY-arkz4ife1AoFGaE1XZCbQ9u45lf5uJt-7bxuG1vbY1GOLL-wKOPlZBB1lz3csZTF1134RjX_IKNpHv2FcBcsdKO0lXOQjUBz20FUHHR9y00IEXRJW5m9Zc43YQBIp0y_sQ_jRBx7xRPyfslxRkdY6k0uL9sU9wbGBNDUVgoSGqeBWJJIyIiEFBmgKYaUyVhnDMgn6mhT14MAKejoE5X0yskUIMtVt4rVt43Cn8rNvgzLrd2lm3sZ90G5xJt8HxO4bvNjH9L97a_Z7TLXsNd8re-uqtbY6uQUvsI9CQrGFZjHAUimocK2KIEBMNghkx5FVoyMoReBm6hUfdwsudwg_PDc7o2LHl_0-Te-dxVchTmrHXcfG7UE-Z23zLymojsN0kWWv_vuKDZ8IXjpHym5xVSa3Hyu_C05Y9Ur4WLErpmo_L9ZyabWsj5S5Knx2OlJYCOOldxN4mTG0Tgz6eBX0y4RNooH4J_KfslU7hR9AtPOoW_tzgjI6du88ugMMXUvk6CNZEyV6S94-4DLX0ebJyKy3U5_buS375q4f79Z1rK9qZS_q8tsIab2-5Nr_9C43yzqs!/dz/d5/L2dBISEvZ0FBIS9nQSEh/?urile=wcm%3Apath%3A%2FPortalNR_Content_ES%2FUsuario%2FTransparencia%2F7.%2BDatos%2Babiertos%2F
[6] https://www.acueducto.com.co/wps/portal/EAB2/Home/ambiente/recurso-hidrico/embalses
[7] https://subredsuroccidente.gov.co/case/el-agua-en-bogota-es-potable-y-segura-para-su-consumo/
[8] http://www.superservicios.gov.co/Transparencia-y-acceso-a-la-informacion-publica/Datos-abiertos
[9] https://www.acueducto.com.co/wps/portal/EAB2/Home/atencion-al-usuario/programacion_cortes
[10] http://www.ideca.gov.co/recursos/historias/los-embalses-que-abastecen-bogota
[11] https://razonpublica.com/crisis-hidrica-bogota-activar-nuevas-formulas-ahorrar-agua/
[12] https://www.datos.gov.co/dataset/Sector-Servicio-Sistema-Acueducto-Bogot-D-C-/8x8w-6v4z/data?no_mobile=true
[13] https://www.aguasdebogota.co/datos-abiertos/
[14] https://datosabiertos.bogota.gov.co/dataset/cuerpo-de-agua-bogota-d-c
[15] https://www.acueducto.com.co/wps/portal/EAB2/Home/transparencia_informacion_publica/datos_abiertos/que+son+los+datos+abiertos
[16] https://www.datos.gov.co/w/y8rv-3phu/dneh-mcp2?cur=wkYBtik3Z5C&from=t1dOjbrnywr
[17] https://www.minvivienda.gov.co
[18] https://www.youtube.com/watch?v=r6Sx89iFfdA
[19] https://datosabiertos.bogota.gov.co/dataset?res_format=CSV&sort=views_recent+desc&organization=eaab
[20] http://www.ideca.gov.co/recursos/mapas/red-matriz-sistema-acueducto
