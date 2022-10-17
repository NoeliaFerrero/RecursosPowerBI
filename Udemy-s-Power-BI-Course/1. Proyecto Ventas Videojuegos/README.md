# 1. Proyecto sobre Ventas de Videojuegos

## Enlace de Demostración:  
[https://app.powerbi.com/view?r=eyJrIjoiNGJlNDI5ZjAtZjFkYy00MzkzLTkzZGItOGJlY2ZkNWM2ZWE5IiwidCI6IjU3N2ZjMWQ4LTA5MjItNDU4ZS04N2JmLWVjNGY0NTVlYjYwMCIsImMiOjR9](https://app.powerbi.com/view?r=eyJrIjoiNGJlNDI5ZjAtZjFkYy00MzkzLTkzZGItOGJlY2ZkNWM2ZWE5IiwidCI6IjU3N2ZjMWQ4LTA5MjItNDU4ZS04N2JmLWVjNGY0NTVlYjYwMCIsImMiOjR9)

## Objetivo
Desarrollar un reporte interactivo que permita analizar las **ventas** de millones de copias de videojuegos a nivel global.

Se requiere poder analizar las ventas a nivel de:
- Año
- Región
- Plataforma
- Género
- Editorial

## Información de Partida
Se proporciona un archivo de Excel llamado **VentasVideojuegos.xlsx**, el cual cuenta con la siguiente estructura:
- **Nombre:** Nombre del videojuego.
- **Plataforma:** Plataforma en la cual el videojuego está disponible.
- **Año:** Año de lanzamiento del videojuego.
- **Editorial:** Editorial del videojuego.
- **Ventas NA:** Ventas (en millones) reportadas en Norteamérica.
- **Ventas EU:** Ventas (en millones) reportadas en Europa.
- **Ventas JP:** Ventas (en millones) reportadas en Japón.
- **Ventas Otros:** Ventas (en millones) reportadas en otras regiones.
- **Ventas Global:** Ventas (en millones) reportadas en todas las regiones.

## Modelamiento Dimensional:
El siguiente modelo ER indica las relaciones entre hechos y dimensiones, además de la estructura de la información como se busca tenerla para analizarla según los objetivos:
![Modelo ER](https://github.com/mamurciac/Udemy-s-Power-BI-Course/blob/master/1.%20Proyecto%20Ventas%20Videojuegos/Modelo%20ER.png)

## Mapa de Transformaciones de Datos (Versión del Video):
- **Encabezados promovidos:** Se usa la primera fila como encabezado.
- **Tipo cambiado:** Se cambian los tipos de datos de las columnas necesarias a un tipo de dato adecuado según su naturaleza.
- **Columnas quitadas:** Se elimina la columna Ventas Global.
- **Columna de anulación de dinamización:** Se aplica anulación de dinamización de columnas a las columnas Ventas NA, Ventas EU, Ventas JP y Ventas Otros.
- **Columnas con nombre cambiado:** Se renombran las columnas Genero por Género, Atributo por Región y Valor por Ventas (Millones).
- **Valor reemplazado:** En la columna Región se reemplaza el valor "Ventas NA" por "Norteamérica".
- **Valor reemplazado:** En la columna Región se reemplaza el valor "Ventas EU" por "Europa".
- **Valor reemplazado:** En la columna Región se reemplaza el valor "Ventas JP" por "Japón".
- **Valor reemplazado:** En la columna Región se reemplaza el valor "Ventas Otros" por "Otros".

## Mapa de Transformaciones de Datos (Versión Optimizada):
- **Encabezados promovidos:** Se usa la primera fila como encabezado.
- **Tipo cambiado:** Se cambian los tipos de datos de las columnas necesarias a un tipo de dato adecuado según su naturaleza.
- **Columnas quitadas:** Se elimina la columna Ventas Global.
- **Columna de anulación de dinamización:** Se aplica anulación de dinamización de columnas a las columnas Ventas NA, Ventas EU, Ventas JP y Ventas Otros.
- **Columnas con nombre cambiado:** Se renombran las columnas Genero por Género y Valor por Ventas (Millones).
- **Columna condicional agregada:** Se llama Región, y se tienen las siguientes condiciones:
	- Si Atributo = "Ventas NA", su nuevo valor es "Norteamérica".
	- Si Atributo = "Ventas EU", su nuevo valor es "Europa".
	- Si Atributo = "Ventas JP", su nuevo valor es "Japón".
	- Si Atributo = "Ventas Otros", su nuevo valor es "Otros".
- **Columnas quitadas:** Se elimina la columna Atributo.
- **Columnas reordenadas:** Se reordenan las columnas necesarias.

## Vista previa del Mapa de Transformaciones:
![Mapa de Transformaciones](https://github.com/mamurciac/Udemy-s-Power-BI-Course/blob/master/1.%20Proyecto%20Ventas%20Videojuegos/Transformaci%C3%B3n%20de%20Datos%20%5BPower%20Query%5D.jpg)

## Modelo de Tablas:
Se verifica la traducción del modelo ER en el modelo relacional o modelo de tablas:
![Modelo Relacional](https://github.com/mamurciac/Udemy-s-Power-BI-Course/blob/master/1.%20Proyecto%20Ventas%20Videojuegos/Modelo%20Relacional.JPG)

## Vista previa del Reporte:
![Vista previa del Reporte](https://github.com/mamurciac/Udemy-s-Power-BI-Course/blob/master/1.%20Proyecto%20Ventas%20Videojuegos/Vista%20del%20Reporte.JPG)