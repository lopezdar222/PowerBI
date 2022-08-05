## Power Query

El editor de Power Query representa la interfaz de usuario de Power Query, donde puede agregar o modificar consultas, administrar consultas agrupando o agregando descripciones a los pasos de consulta o visualizar las consultas y su estructura con diferentes vistas. La interfaz de usuario de Power Query tiene cinco componentes distintos.

![Editor](https://docs.microsoft.com/en-us/power-query/media/power-query-ui/pqui-user-interface.png)

- Cinta de opciones: la experiencia de navegación de la cinta de opciones, que proporciona varias pestañas para agregar transformaciones, seleccionar opciones para su consulta y acceder a diferentes botones de la cinta para completar varias tareas.
- Panel de consultas: una vista de todas las consultas disponibles.
- Vista actual: su vista de trabajo principal, que de forma predeterminada, muestra una vista previa de los datos de su consulta.
- Configuración de consulta: una vista de la consulta seleccionada actualmente con información relevante, como el nombre de la consulta, los pasos de la consulta y varios indicadores.
- Barra de estado: una barra que muestra información importante relevante sobre la consulta, como el tiempo de ejecución, el total de columnas y filas, y el estado de procesamiento. Esta barra también contiene botones para cambiar la vista actual.

#### La cinta de opciones

La cinta de opciones es el componente donde encontrará la mayoría de las transformaciones y acciones que puede realizar en el editor de Power Query. Tiene múltiples pestañas, cuyos valores dependen de la integración del producto. Cada una de las pestañas proporciona botones y opciones específicos, algunos de los cuales pueden ser redundantes en toda la experiencia de Power Query. Estos botones y opciones le proporcionan un fácil acceso a las transformaciones y acciones que pueda necesitar.

![Cinta](https://docs.microsoft.com/en-us/power-query/media/power-query-ui/standard-ribbon.png)


[Power Query](https://docs.microsoft.com/en-us/power-query/power-query-ui)

#### Elaboración de perfiles de datos

Otra característica de Power Query que puede ayudarle a comprender mejor sus datos es la generación de perfiles de datos. Al habilitar las funciones de generación de perfiles de datos, obtendrá comentarios sobre los datos dentro de los campos de consulta, como la distribución de valores, la calidad de la columna y más.

Le recomendamos que utilice esta función durante todo el desarrollo de sus consultas, pero siempre puede habilitar y deshabilitar la función a su conveniencia. La siguiente imagen muestra todas las herramientas de generación de perfiles de datos habilitadas para la consulta de análisis de país.

[Perfiles de datos](https://docs.microsoft.com/en-us/power-query/media/power-query-ui/pqui-data-profiling.png)

#### El editor avanzado
Si desea observar el código que el editor de Power Query está creando con cada paso, o desea crear su propio código de conformación, puede usar el editor avanzado. Para abrir el editor avanzado, seleccione la pestaña Ver en la cinta de opciones y, a continuación, seleccione Editor avanzado. Aparece una ventana que muestra el código de consulta existente.## Homework

[Editor](https://docs.microsoft.com/en-us/power-query/media/power-query-ui/queryoverview_advancededitor.png)

#### Pasos aplicados
Cada transformación que se aplica a la consulta se guarda como un paso en la sección Pasos aplicados del panel de configuración de la consulta. Si alguna vez necesita comprobar cómo se transforma la consulta de paso a paso, puede seleccionar un paso y obtener una vista previa de cómo se resuelve la consulta en ese momento específico.

También puede hacer clic con el botón secundario en una consulta y seleccionar la opción Propiedades para cambiar el nombre de la consulta o agregar una descripción para la consulta.

#### Agregar una nueva columna
Con los datos de clientes y proveedores en una sola tabla, ahora puede calcular la proporción de clientes a proveedores para cada país. Seleccione el último paso de la consulta Análisis de país y, a continuación, seleccione las columnas Clientes y Proveedores. En la pestaña Agregar columna de la cinta de opciones y dentro del grupo de números De, seleccione Estándar y, a continuación, Dividir (entero) en el menú desplegable.

#### Uso de la lista Pasos aplicados

Cualquier transformación en sus datos se mostrará en la lista Pasos aplicados. Por ejemplo, si cambia el nombre de una columna, se mostrará en la lista Pasos aplicados como Columnas renombradas.<br>
Al seleccionar cualquier paso, se le mostrarán los resultados de ese paso en particular, para que pueda ver exactamente cómo cambian sus datos a medida que agrega pasos a la consulta.

![Pasos](https://docs.microsoft.com/en-us/power-query/images/applied-steps-new-column-name.png)

Para eliminar un paso, haga clic con el botón secundario en el paso y seleccione Eliminar.

![Eliminar](https://docs.microsoft.com/en-us/power-query/images/applied-steps-delete.png)

Para editar el paso, haga clic con el botón secundario en el paso y seleccione Propiedades.

![Editar](https://docs.microsoft.com/en-us/power-query/applied-steps)

![Propiedades](https://docs.microsoft.com/en-us/power-query/images/applied-steps-properties.png)

Para cambiar el nombre de un paso, haga clic con el botón secundario en el paso y seleccione Cambiar nombre.

![Nombre](https://docs.microsoft.com/en-us/power-query/images/applied-steps-rename.png)


## Herramientas de Power Query
Dentro de la documentación oficial de Power Query, encontraras una sección específica para la "Transformación de datos" y dentro de esta sección herramientas para transformar tablas y columnas, agregar columnas, combinar datos y dividir columnas.<br>
Te recomendamos leer al menos las siguientes herramientas que te serán útiles a la hora de realizar transformaciones en Power Query:<br>

### [Documentación Oficial - Power Query](https://docs.microsoft.com/en-us/power-query/)


#### [Promover encabezados](https://docs.microsoft.com/en-us/power-query/table-promote-demote-headers)

#### [Elegir o quitar columnas](https://docs.microsoft.com/en-us/power-query/choose-remove-columns) 

#### [Tipos de datos](https://docs.microsoft.com/en-us/power-query/data-types)

#### [Errores](https://docs.microsoft.com/en-us/power-query/dealing-with-errors)

#### [Reemplazar valores](https://docs.microsoft.com/en-us/power-query/replace-values)

#### [Agregar columna personalizada](https://docs.microsoft.com/en-us/power-query/add-custom-column)

#### [Columna condicional](https://docs.microsoft.com/en-us/power-query/add-conditional-column)

#### [Anexar consultas](https://docs.microsoft.com/en-us/power-query/append-queries)

#### [Combinar consultas](https://docs.microsoft.com/en-us/power-query/merge-queries-overview)