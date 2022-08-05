## Power Query Avanzado

Power Query proporciona una potente experiencia de "obtención de datos" que abarca muchas características. Una capacidad principal de Power Query es filtrar y combinar, es decir, "mezclar" datos de uno o más de una rica colección de orígenes de datos compatibles. Cualquier mashup de datos de este tipo se expresa utilizando el lenguaje de fórmulas de Power Query (conocido informalmente como "M"). Power Query incrusta documentos M en libros de Excel y Power BI para habilitar la combinación repetible de datos.

Este documento proporciona la especificación para M. Después de una breve introducción que tiene como objetivo construir una primera intuición y familiaridad con el idioma, el documento cubre el lenguaje precisamente en varios pasos progresivos:

- La estructura léxica define el conjunto de textos que son léxicamente válidos.

- Valores, expresiones, entornos y variables, identificadores y el modelo de evaluación forman los conceptos básicos del lenguaje.

- La especificación detallada de los valores, tanto primitivos como estructurados, define el dominio de destino del lenguaje.

- Los valores tienen tipos, en sí mismos un tipo especial de valor, que caracterizan los tipos fundamentales de valores y llevan metadatos adicionales que son específicos de las formas de los valores estructurados.

- El conjunto de operadores en M define qué tipos de expresiones se pueden formar.

- Las funciones, otro tipo de valores especiales, proporcionan la base para una rica biblioteca estándar para M y permiten la adición de nuevas abstracciones.

- Pueden producirse errores al aplicar operadores o funciones durante la evaluación de la expresión. Si bien los errores no son valores, hay formas de controlar los errores que asignan los errores a los valores.

- Permita que las expresiones permitan la introducción de definiciones auxiliares utilizadas para crear expresiones complejas en pasos más pequeños.

- Si las expresiones admiten la evaluación condicional.

- Las secciones proporcionan un mecanismo de modularidad simple. (Power Query aún no aprovecha las secciones).

- Finalmente, una gramática consolidada recoge los fragmentos gramaticales de todas las demás secciones de este documento en una sola definición completa.

Para ver un detalle de cada punto puede ingresar aquí:<br>
[Introducción a M](https://docs.microsoft.com/en-us/powerquery-m/m-spec-introduction).<br>

### Funciones

En M, una función es una asignación de un conjunto de valores de entrada a un único valor de salida. Una función se escribe nombrando primero el conjunto requerido de valores de entrada (los parámetros de la función) y luego proporcionando una expresión que calculará el resultado de la función utilizando esos valores de entrada (el cuerpo de la función) después del símbolo =>. <br>

Cuando nos referimos a una función predeterminada, hablamos de un valor que representa una asignación de un conjunto de valores de argumento a un solo valor. Una función se invoca proporcionando un conjunto de valores de entrada (los valores del argumento) y produce un único valor de salida (el valor devuelto).

Una consulta de lenguaje de fórmula M de Power Query se compone de pasos de expresión de fórmula que crean una consulta de mashup. Una expresión de fórmula puede ser evaluada (calculada), produciendo un valor. La expresión let encapsula un conjunto de valores que se van a calcular, se asignan nombres y, a continuación, se usan en una expresión posterior que sigue a la instrucción in. Por ejemplo, una expresión let podría contener una variable Source que sea igual al valor de Text.Proper() y produzca un valor de texto en mayúsculas y minúsculas.
```M
let  
    Source = Text.Proper("hello world")  
in  
    Source  
```

### Biblioteca
M incluye un conjunto común de definiciones disponibles para su uso desde una expresión llamada biblioteca estándar (al igual que las funciones en Excel), o simplemente biblioteca para abreviar. Estas definiciones consisten en un conjunto de valores con nombre.

La documentación de las funciones M de Power Query incluye artículos para cada una de las más de 700 funciones. Algunas de las más importantes son las que nos permiten acceder a fuentes de datos:<br>
- [Web Contents](https://docs.microsoft.com/en-us/powerquery-m/web-contents)<br>
Esta función permite conexiones a API´s y entender su funcionamiento ayuda a extraer datos disponibilizados mediante ellas.


- [XML Tables](https://docs.microsoft.com/en-us/powerquery-m/xml-tables). <br>
- [JSON Document](https://docs.microsoft.com/en-us/powerquery-m/json-document).<br>
- [CSV Document](https://docs.microsoft.com/en-us/powerquery-m/csv-document).<br>

También existe una categoría de funciones de listas, que nos permiten utilizar los datos de una fuente como argumentos en otra consulta:

[Lista Dates](https://docs.microsoft.com/en-us/powerquery-m/list-dates).<br>
[List Max](https://docs.microsoft.com/en-us/powerquery-m/list-max).<br>
[List Min](https://docs.microsoft.com/en-us/powerquery-m/list-min).<br>
[Lista Range](https://docs.microsoft.com/en-us/powerquery-m/list-range).<br>
[Lista Generate](https://docs.microsoft.com/en-us/powerquery-m/list-generate).<br>

Los argumentos de una función en M pueden ser reemplazados por parámetros, esto permite que dicho argumento pueda ser dinpamico o reemplazado de manera sencilla.<br>
[Parámetros en M](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-dynamic-m-query-parameters)

Simpre debe tener en cuenta que M es un lenguaje que distingue entre mayúsculas y minúsculas.

### Consultas avanzadas

Para crear una consulta avanzada, utilice el Editor de consultas. Una consulta de mashup se compone de variables, expresiones y valores encapsulados por una expresión let. Una variable puede contener espacios utilizando el identificador # con el nombre entre comillas como en #"Nombre de variable".

Una expresión let sigue esta estructura:

```M
let  
   Variablename = expression,  
   #"Variable name" = expression2  
in   
   Variablename
```

Para crear una consulta M en el Editor de consultas, siga este proceso básico:

- Cree una serie de pasos de fórmula de consulta que comiencen con la instrucción let. Cada paso está definido por un nombre de variable de paso. Una variable M puede incluir espacios utilizando el carácter # como #"Nombre del paso". Un paso de fórmula puede ser una fórmula personalizada. Tenga en cuenta que el lenguaje de fórmulas de Power Query distingue entre mayúsculas y minúsculas.
- Cada paso de la fórmula de consulta se basa en un paso anterior haciendo referencia a un paso por su nombre de variable.
- Genere un paso de fórmula de consulta mediante la instrucción in. Generalmente, el último paso de consulta se utiliza como resultado final del conjunto de datos.


[Condicionales en M](https://docs.microsoft.com/en-us/powerquery-m/m-spec-conditionals).<br>
[Recorrido por M](https://docs.microsoft.com/en-us/powerquery-m/quick-tour-of-the-power-query-m-formula-language).<br>
[Expresiones en M](https://docs.microsoft.com/en-us/powerquery-m/expressions-values-and-let-expression).<br>

## Modelo relacional Power BI

### Crear y administrar relaciones en Power BI Desktop

Cuando se importan varias tablas, es probable que se realice algún análisis utilizando datos de todas esas tablas. Las relaciones entre esas tablas son necesarias para calcular con precisión los resultados y mostrar la información correcta en los informes. Power BI Desktop facilita la creación de esas relaciones. De hecho, en la mayoría de los casos no tendrá que hacer nada, la función de detección automática lo hace por usted. Sin embargo, a veces es posible que tenga que crear relaciones usted mismo o que necesite hacer cambios en una relación. De cualquier manera, es importante comprender las relaciones en Power BI Desktop y cómo crearlas y editarlas.

### Detección automática durante la carga
Si consulta dos o más tablas al mismo tiempo, cuando se cargan los datos, Power BI Desktop intenta buscar y crear relaciones por usted. Las opciones de relación Cardinalidad, Dirección de filtro cruzado y Activar esta relación se establecen automáticamente. Power BI Desktop examina los nombres de columna de las tablas que está consultando para determinar si hay relaciones potenciales. Si las hay, esas relaciones se crean automáticamente. Si Power BI Desktop no puede determinar con un alto nivel de confianza que hay una coincidencia, no crea la relación. Sin embargo, aún puede utilizar el cuadro de diálogo Administrar relaciones para crear o editar relaciones manualmente.

![Relaciones](/_src/assets/relaciones.gif)

Es importante destacar que muchas veces, las relaciones creadas por Power BI, no suelen ser las esperadas. Por eso es muy importante observar el modelo final y realizar las correcciones necesarias.

### Crear una relación manualmente
En la pestaña Modelado, seleccione Administrar relaciones > Nuevo.

En el cuadro de diálogo Crear relación, en la lista desplegable primera tabla, seleccione una tabla. Seleccione la columna que desea utilizar en la relación.

En la segunda lista desplegable de tablas, seleccione la otra tabla que desee en la relación. Seleccione la otra columna que desea usar y, a continuación, seleccione Aceptar.

![Relaciones 2](/_src/assets/relaciones2.gif)

#### Cardinalidad
La opción Cardinalidad puede tener una de las siguientes configuraciones:

Muchos a uno (*:1):Una relación de muchos a uno es el tipo de relación más común y predeterminado. Significa que la columna de una tabla dada puede tener más de una instancia de un valor, y la otra tabla relacionada, a menudo conocida como la tabla de búsqueda, tiene solo una instancia de un valor.

Uno a uno (1:1): En una relación uno a uno, la columna de una tabla tiene solo una instancia de un valor particular, y la otra tabla relacionada tiene solo una instancia de un valor particular.

Uno a muchos (1:*): En una relación de uno a muchos, la columna de una tabla tiene solo una instancia de un valor determinado, y la otra tabla relacionada puede tener más de una instancia de un valor.

Muchos a muchos (*:*):Con los modelos compuestos, puede establecer una relación de muchos a muchos entre tablas, lo que elimina los requisitos para valores únicos en las tablas. También elimina soluciones anteriores, como la introducción de nuevas tablas solo para establecer relaciones. Para obtener más información, consulte Relaciones con una cardinalidad de muchos-muchos.

Para obtener más información acerca de cuándo cambiar la cardinalidad, consulte Descripción de las opciones adicionales.

#### Dirección del filtro cruzado

La opción Dirección de filtro cruzado puede tener una de las siguientes configuraciones:

Ambos: Para fines de filtrado, ambas tablas se tratan como si fueran una sola tabla. La configuración Ambos funciona bien con una sola tabla que tiene muchas tablas de búsqueda que la rodean. Un ejemplo es una tabla de datos reales de ventas con una tabla de búsqueda para su departamento. Esta configuración a menudo se denomina configuración de esquema en estrella (una tabla central con varias tablas de búsqueda). Sin embargo, si tiene dos o más tablas que también tienen tablas de búsqueda (con algunas en común), entonces no querrá usar la configuración Ambos. Para continuar con el ejemplo anterior, en este caso, también tiene una tabla de ventas de presupuesto que registra el presupuesto objetivo para cada departamento. Y, la tabla del departamento está conectada tanto a la tabla de ventas como a la tabla de presupuesto. Evite la opción Ambos para este tipo de configuración.

Único: la dirección predeterminada más común, lo que significa que las opciones de filtrado en las tablas conectadas funcionan en la tabla donde se agregan los valores. Si importa un power pivot en Excel 2013 o un modelo de datos anterior, todas las relaciones tendrán una sola dirección.

Para obtener más información acerca de cuándo cambiar la dirección del filtro cruzado, consulte Descripción de las opciones adicionales.

### Propósito de la relación
Una relación de modelo propaga los filtros aplicados en la columna de una tabla de modelo a una tabla de modelo diferente. Los filtros se propagarán siempre que haya una ruta de relación a seguir, lo que puede implicar la propagación a varias tablas.

Las rutas de relación son deterministas, lo que significa que los filtros siempre se propagan de la misma manera y sin variación aleatoria. Sin embargo, las relaciones pueden deshabilitarse o modificar el contexto del filtro mediante cálculos de modelos que utilizan funciones DAX concretas (concepto que veremos más adelante).

Las relaciones de modelo no imponen la integridad de los datos. Para obtener más información, vea el tema Evaluación de relaciones más adelante en este artículo, que explica cómo se comportan las relaciones de modelo cuando hay problemas de integridad de datos con los datos.

![Modelos](/_src/assets/filtro.gif)

#### Este tema te ayudará a genera mejores modelos análiticos en Power BI, por eso es importante que profundizes con la documentación oficial:

[Relaciones en Power BI](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-create-and-manage-relationships)