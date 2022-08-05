## Conceptos básicos de DAX en Power BI Desktop

[Tutorial DAX](https://docs.microsoft.com/en-us/dax/)

Al utilizar Power BI para crear informes sencillos, puede que no sea necesario realizar un cálculo de medidas. Solo con arrastar el campo, Power BI da una serie de opciones de cálculo rápido tales como: suma, cuenta, promedio, máximo mínimo. También puede acceder a la opción de cálculo de "médidas rápidas": <br>
[Medidas rápidas en Power BI](https://docs.microsoft.com/es-es/power-bi/transform-model/desktop-tutorial-create-measures) 

Lo cierto es que si pretende realizar análisis complejos en el modelo desarrollado, será muy importante familirizarse con la sintaxis de DAX.

DAX es una colección de funciones, operadores y constantes que se pueden usar en una fórmula o expresión para calcular y devolver uno o más valores. Dicho de manera más simple, DAX le ayuda a crear nueva información a partir de datos que ya están en su modelo.

Es fácil crear un nuevo archivo de Power BI Desktop e importar algunos datos en él. Incluso puede crear informes que muestren información valiosa sin usar ninguna fórmula DAX. Pero, ¿qué pasa si necesita analizar el porcentaje de crecimiento en todas las categorías de productos y para diferentes rangos de fechas? ¿O necesita calcular el crecimiento año tras año en comparación con las tendencias del mercado? Las fórmulas DAX proporcionan esta capacidad y muchas otras capacidades importantes también. Aprender a crear fórmulas DAX efectivas le ayudará a sacar el máximo provecho de sus datos. Cuando obtenga la información que necesita, puede comenzar a resolver problemas comerciales reales que afectan sus resultados. Este es el poder de Power BI, y DAX le ayudará a llegar allí.

Existen tres conceptos fundamentales relacionados a DAX: sintaxis, funciones y contexto. Hay otros conceptos importantes en DAX, pero comprender estos tres conceptos proporcionará la mejor base sobre la cual desarrollar sus habilidades de DAX.

### Sintaxis

Antes de crear sus propias fórmulas, echemos un vistazo a la sintaxis de la fórmula DAX. La sintaxis incluye los diversos elementos que componen una fórmula, o más simplemente, cómo se escribe la fórmula. Por ejemplo, aquí hay una fórmula DAX simple para una medida:

![DAX](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-quickstart-learn-dax-basics/qsdax_1_syntax.png)

Esta fórmula incluye los siguientes elementos de sintaxis:

- A. El nombre de la medida, Ventas totales.

- B. El operador de signo igual (=), que indica el comienzo de la fórmula. Cuando se calcula, devolverá un resultado.

- C. La función DAX SUM, que suma todos los números de la columna Sales[SalesAmount].

- D. Paréntesis (), que rodean una expresión que contiene uno o más argumentos. La mayoría de las funciones requieren al menos un argumento. Un argumento pasa un valor a una función.

- E. La tabla a la que se hace referencia, Ventas.

- F. La columna a la que se hace referencia, [SalesAmount], en la tabla Sales. Con este argumento, la función SUM sabe en qué columna agregar una SUMA.

Al tratar de entender una fórmula DAX, a menudo es útil desglosar cada uno de los elementos en un idioma que piense y hable todos los días. Por ejemplo, puede leer esta fórmula como:

Para la medida denominada Ventas totales, calcule (=) la SUMA de valores en la columna [SalesAmount ] de la tabla Ventas.

### Medidas rápidas vs medidas cálculadas

Es posible que pienses: "¿No está esta medida haciendo lo mismo que si simplemente agregara el campo SalesAmount a mi informe?" Bueno, sí. Pero, hay una buena razón para crear nuestra propia medida que resume los valores del campo SalesAmount: podemos usarlo como argumento en otras fórmulas. Esto puede parecer un poco confuso ahora, pero a medida que sus habilidades con la fórmula DAX crecen, conocer esta medida hará que sus fórmulas y su modelo sean más eficientes.

## Funciones

DAX incluye las siguientes categorías de funciones: Fecha y hora, Inteligencia de tiempo, Información, Lógica, Matemática, Estadística, Texto, Padre/Hijo y Otras funciones. Si está familiarizado con las funciones de las fórmulas de Excel, muchas de las funciones de DAX le parecerán similares; sin embargo, las funciones de DAX son únicas de las siguientes maneras:

Una función DAX siempre hace referencia a una columna completa o a una tabla. Si desea utilizar sólo valores concretos de una tabla o columna, puede agregar filtros a la fórmula.

Si necesita personalizar los cálculos fila por fila, DAX proporciona funciones que le permiten utilizar el valor de fila actual o un valor relacionado como una especie de argumento, para realizar cálculos que varían según el contexto. Aprenderás más sobre el contexto más adelante.

DAX incluye muchas funciones que devuelven una tabla en lugar de un valor. La tabla no se muestra, pero se utiliza para proporcionar entrada a otras funciones. Por ejemplo, puede recuperar una tabla y, a continuación, contar los distintos valores que contiene, o calcular sumas dinámicas en tablas o columnas filtradas.

DAX incluye una variedad de funciones de inteligencia de tiempo. Estas funciones le permiten definir o seleccionar intervalos de fechas y realizar cálculos dinámicos basados en ellos. Por ejemplo, puede comparar sumas entre períodos paralelos.

Excel tiene una función popular, BUSCARV. Las funciones DAX no toman una celda o un rango de celdas como referencia como lo hace BUSCARV en Excel. Las funciones DAX toman una columna o una tabla como referencia. Tenga en cuenta que en Power BI Desktop está trabajando con un modelo de datos relacional. Buscar valores en otra tabla es fácil, y en la mayoría de los casos no es necesario crear ninguna fórmula en absoluto.

Como puede ver, las funciones de DAX pueden ayudarle a crear fórmulas potentes. Realmente solo tocamos los conceptos básicos de las funciones. A medida que sus habilidades de DAX crecen, creará fórmulas utilizando muchas funciones diferentes. Uno de los mejores lugares para obtener detalles sobre cada una de las funciones de DAX es en la Referencia de funciones de DAX.

## Crear columnas calculadas en Power BI Desktop

A veces los datos que está analizando no contienen un determinado campo necesario para obtener los resultados buscados. Aquí es donde entran en escena las columnas calculadas. Las columnas calculadas utilizan fórmulas de expresiones de análisis de datos (DAX) para definir los valores de una columna, cualquier cosa desde poner juntos valores de texto de un par de columnas diferentes hasta calcular un valor numérico a partir de otros valores. Por ejemplo, supongamos que sus datos tienen los campos Ciudad y Estado, pero desea un único campo Ubicación que tenga ambos, como "Miami, Florida". Para esto es precisamente que sirven las columnas calculadas.

Las columnas calculadas son similares a las medidas en que ambas se basan en fórmulas DAX, pero difieren en cómo se usan. A menudo se usan medidas en el área Valores de una visualización para calcular los resultados en función de otros campos. Las columnas calculadas se usan como nuevos Campos en filas, ejes, leyendas y áreas de grupos de visualizaciones.

#### [Creación de una columna calculada con valores de tablas relacionadas](https://docs.microsoft.com/es-es/power-bi/transform-model/desktop-tutorial-create-calculated-columns#create-a-calculated-column-with-values-from-related-tables)

#### [Columna cálculada con IF](https://docs.microsoft.com/es-es/power-bi/transform-model/desktop-tutorial-create-calculated-columns#create-a-calculated-column-that-uses-an-if-function)

## Contexto de las fórmulas DAX

[Contextos](https://support.microsoft.com/es-es/office/contexto-de-las-f%C3%B3rmulas-dax-2728fae0-8309-45b6-9d32-1d600440a7ad#:~:text=El%20contexto%20le%20permite%20realizar,y%20tambi%C3%A9n%20los%20datos%20relacionados.)

Si bien el siguiente extracto corresponde a documentación oficial de Power Pivot, los conceptos aplican a Power BI debido a que este software de BI se origina mediante la combinación de Power Pivot, Power Query y Power View.

El contexto le permite realizar análisis dinámicos, en los que los resultados de una fórmula pueden cambiar para reflejar la selección de fila o celda actual, y también los datos relacionados. Entender lo que es el contexto y usarlo eficazmente es muy importante para generar fórmulas muy eficaces, y para solucionar los posibles problemas de las fórmulas.

Los diferentes tipos de contexto son: contexto de la fila, contexto del filtro y contexto de transición (este último lo veremos más adelante). 

### Descripción de contexto

Las fórmulas de Power BI pueden verse afectadas por los filtros aplicados en un objeto visual, por relaciones entre las tablas y por filtros utilizados en fórmulas. El contexto es aquello que permite llevar a cabo análisis dinámicos.


El contexto de fila se puede entender como "la fila actual". Si ha creado una columna calculada, el contexto de la fila está formado por los valores de cada fila individual y los valores de las columnas que están relacionadas con la fila actual. También hay algunas funciones(EARLIER y EARLIEST) que obtienen un valor de la fila actual y, a continuación, usan ese valor mientras realizan una operación sobre toda una tabla.a.

El contexto de filtro es el conjunto de valores permitido en cada columna, basado en las restricciones de filtro que se aplicaron a la fila o que se han definido por expresiones de filtro dentro de la fórmula.

Activa la traducción automática y mira estos conceptos:

#### [Contexto de fila](https://www.youtube.com/watch?v=Nm9x83J-SBk)

#### [Contexto de filtro](https://www.youtube.com/watch?v=lX2ztEh3tuA)


[Documentación DAX](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-quickstart-learn-dax-basics)

[Columnas calculadas](https://docs.microsoft.com/es-es/power-bi/transform-model/desktop-tutorial-create-calculated-columns)

## Funciones importantes de DAX

### CALCULATE

[Tutorial - CALCULATE](https://www.youtube.com/watch?v=6lcZ5J-2NRQ)

[Función CACULATE](https://docs.microsoft.com/en-us/dax/calculate-function-dax)

### FILTER

[Tutorial FILTER](https://www.youtube.com/watch?v=ISf41o1FF10)

[Función FILTER](https://docs.microsoft.com/en-us/dax/filter-function-dax)

### Inteligencia de tiempo

[PREVIOUSMONTH](https://docs.microsoft.com/en-us/dax/previousmonth-function-dax)

[PREVIOUSYEAR](https://docs.microsoft.com/en-us/dax/previousyear-function-dax)

[SAMEPERIODLASTYEAR](https://docs.microsoft.com/en-us/dax/sameperiodlastyear-function-dax)

[Tutorial ejemplo - Inteligencia de tiempo](https://www.youtube.com/watch?v=bmI8p8Z9ps4)

[Funciones de inteligencia de tiempo](https://docs.microsoft.com/en-us/dax/time-intelligence-functions-dax)

### [Funciones de agregación](https://docs.microsoft.com/en-us/dax/aggregation-functions-dax)

### [Funciones de tiempo](https://docs.microsoft.com/en-us/dax/date-and-time-functions-dax)