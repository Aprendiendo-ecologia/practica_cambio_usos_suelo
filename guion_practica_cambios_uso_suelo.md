**Práctica de manejo de bases de datos relacionales y SIG con objeto de
caracterizar los cambios de uso del suelo.**

**Ecología aplicada.** Curso 2017-2018.

*Francisco Javier Bonet-García (fjbonet@gmail.com)*

***Introducción y fuentes de datos a utilizar***

Una de las principales manifestaciones de la actividad humana sobre la
biosfera es el cambio de uso del suelo. Roturamos bosques para cultivar
y crear pastos. Modificamos el curso de los ríos para obtener agua y
producir electricidad. Creamos ciudades que sellan el suelo fértil y un
largo etcétera. De hecho, el cambio de usos del suelo es considerado
como uno de los principales motores del cambio global en el Antropoceno.
La caracterización cuantitativa y cualitativa de los cambios de uso del
suelo es, por tanto, fundamental para entender cómo nuestra actividad
está modificando la estructura y funcionamiento de los ecosistemas.

En esta práctica aprenderemos algunas técnicas útiles, entre otras
cosas, para caracterizar los cambios de uso del suelo. En concreto
trabajaremos con bases de datos relacionales y con sistemas de
información geográfica.

La zona de estudio para la práctica será la zona norte de la ciudad de
Córdoba y las áreas de vegetación natural que hay hasta Los Villares. En
esta zona caracterizaremos los cambios de uso del suelo ocurridos desde
1956 hasta 2007.

Durante el desarrollo de la práctica nos centraremos en caracterizar los
cambios estructurales en los usos del suelo. Esto quiere decir que solo
evaluaremos si una zona determinada ha cambiado de uso del suelo o no y
cómo ha sido ese cambio. Esto implica que no tendremos en cuenta los
cambios en el funcionamiento. Es decir, no analizaremos si un encinar,
por ejemplo, tiene un funcionamiento ecosistémico invariable entre 1999
y 2007.

Para ello utilizaremos dos siguientes fuentes de información:

1.  Mapa de usos y coberturas vegetales del suelo. Este mapa se elabora
    periódicamente por parte de la Consejería de Medio Ambiente y
    Ordenación del Territorio de la Junta de Andalucía a través de la
    REDIAM (Red de Información Ambiental). Se trata de un mapa de
    carácter vectorial con escala 1:25.000 y que tiene una estructura de
    datos como la que se muestra en el siguiente esquema. El mapa recoge
    información de los usos del suelo de todo el territorio andaluz
    desde 1956 hasta 2007, por lo que se trata de un mapa multitemporal.
    Puede descargarse gratuitamente de internet siguiendo
    [este](http://www.juntadeandalucia.es/medioambiente/site/rediam/menuitem.04dc44281e5d53cf8ca78ca731525ea0/?vgnextoid=635a762646e2a410VgnVCM1000001325e50aRCRD&vgnextchannel=39174e0623f6c410VgnVCM2000000624e50aRCRD&vgnextfmt=rediam&lr=lang_es) enlace.

> <img src="https://github.com/Aprendiendo-ecologia/practica_cambio_usos_suelo/raw/main/downloadable_files/images/Modatos.png" alt="modelo de datos" style="zoom:75%;" />

Para simplificar un poco el manejo de esta gran fuente de información
(contiene miles de polígonos en toda Andalucía) usaremos únicamente los
siguientes elementos:

-   mucva25_zona.shp (.dbf, .prj, .qpj, .shx): Es un fichero de formas
    (capa de información vectorial) que cubre el norte de la ciudad de
    Córdoba y las zonas boscosas de los alrededores. Será nuestra fuente
    principal de datos.

-   Usos_niveles.mdb: se trata de una base de datos en formato Microsoft
    Access que contiene varias tablas. La única que usaremos (las demás
    son pruebas para que las editéis sin riesgo) se llama USOS_NIVELES y
    contiene la leyenda del mapa anterior (ver tabla abajo). Cada clase
    de la leyenda (formación vegetal o uso del suelo) tiene un código
    único.

<img src="https://github.com/Aprendiendo-ecologia/practica_cambio_usos_suelo/raw/main/downloadable_files/images/dic_usos.png" alt="modelo de datos" style="zoom:75%;" />

2.  Ortofotografías: con objeto de visualizar la zona de estudio con
    detalle se usarán las fotografías aéreas ortorectificadas que crean
    periódicamente la REDIAM y otras instituciones estatales a través
    del Plan Nacional de Ortofotografía Aérea (PNOA). Accederemos a los
    servicios WMS de ortofotos creados por la REDIAM a través de
    [este](http://www.juntadeandalucia.es/medioambiente/site/rediam/menuitem.aedc2250f6db83cf8ca78ca731525ea0/?vgnextoid=eab1d61d8470f210VgnVCM2000000624e50aRCRD) enlace.

***Objetivos***

El objetivo general de esta práctica es caracterizar los cambios de uso
del suelo ocurridos en la zona de estudio desde 1956 hasta la actualidad
(bueno, hasta 2007). De manera más concreta, se abordarán las siguientes
cuestiones:

-   ¿Qué porcentaje del terreno ha cambiado de uso entre 1956 y 2007?

-   ¿En qué periodo histórico desde 1956 hasta 2007 han ocurrido cambios
    más intensos?

-   ¿Es posible identificar zonas específicas donde las trayectorias de
    cambio de uso hayan sido hacia una mayor complejidad estructural de
    la vegetación (avance sucesional) o viceversa?

***Plan de trabajo***

El trabajo se realizará en tres sesiones prácticas de dos horas de
duración cada una. Para responder a las preguntas anteriores generaremos
dos mapas de cambio. El primero de ellos mostrará de forma discreta
(también denominada binaria) los cambios entre los distintos años para
los que tenemos información en el mapa de partida. Se trata de un mapa
en el que solo sabremos si en un polígono dado ha habido o no cambios de
uso del suelo. El siguiente mapa será un poco más complejo porque nos
permitirá conocer si el cambio ocurrido ha sido hacia un estado más
complejo de la vegetación o al contrario. Para generar este mapa
continuo tendremos que trabajar con QGIS y con Access.

La siguiente secuencia muestra los pasos a dar, que están descritos a través de varios videos y presentaciones.

-   Generalidades de SIG. Cómo cargar una capa vectorial y servicios
    WMS.

-   Estructura del mapa de usos y coberturas vegetales de Andalucía.

-   Explicación del flujo de trabajo (secuencia de tareas) aplicado para
    realizar el mapa binario.

-   Paso a paso con QGIS para generar el mapa continuo de cambios.

-   Explicación del flujo de trabajo aplicado para realizar el mapa
    continuo de cambios.

***Documentación y ayuda***
Toda esta práctica está explicada en los siguientes videos.

***Material a entregar***

La entrega se hará a través del formulario que hay en el moodle. Aquí se detalla el material a elaborar y se  dan algunas pistas que os serán útiles...

+ Porcentajes de cambio entre cada lapso de tiempo del mapa de vegetación. Deberéis de entregar un archivo de Excel con una tabla  que muestre qué porcentaje de la superficie de la zona de estudio ha cambiado de uso en cada lapso de tiempo. Sería una tabla parecida a la que se muestra abajo.

| Lapso de tiempo | 56-77 | 77-84 | 84-99 | 99-03 | 03-07 |
| --------------- | ----- | ----- | ----- | ----- | ----- |
|        % con cambio         |  ...     |  ...     |  ...     |  ...     |  ...     |
| % sin cambio |  ...     |  ...     |  ...     |  ...     |  ...     |




Para hacer esta tabla tendréis que hacer lo siguiente:

+ Repetir el procedimiento de generación del mapa binario creando tantos campos como lapsos de tiempo hay (los mismos que la tabla superior). En el video de youtube podéis ver cómo se hace esto entre 1956 y 2007. En este caso debéis de repetir esto tantas veces como lapsos. Esto generará un mapa de vegetación con varios campos nuevos.

-   Desde el explorador de Windows debéis duplicar el archivo dbf que forma parte del shapefile anterior. Así evitamos que al modificar dicho dbf alteremos el fichero de formas.
    
-   Abrimos el dbf con Excel y lo guardamos en formato Excel.

-   Borramos todos los campos menos los anteriormente comentados y el campo \"shape_Area\" que muestra la superficie de cada polígono.
    
-   Ahora, mediante filtros y otras técnicas que debéis conocer, podréis generar la tabla superior.  Básicamente se trata de sumar la superficie de los polígonos con y sin cambio en cada lapso de los anteriores. Luego calcularemos el porcentaje de cambio teniendo en cuenta la superficie de todos los polígonos.
    
-   Interpretación biológica de los cambios observados. Debéis describir en un sencillo párrafo cuál es la interpretación biológica que dais a los resultados obtenidos. Para ello deberás de tener en cuenta en
    qué lapso de tiempo ha habido más cambio de usos, o en qué zonas se concentran los cambios, etc.
    
-   Incluye un pantallazo del mapa de trayectorias sucesionales entre 1956 y 2007 que hayas creado. Incluye también la leyenda para poder interpretarlo.
    
-   Interpreta la distribución espacial de los procesos de \"avance sucesional\" y \"retroceso sucesional\" a la luz de tus conocimientos sobre el fenómeno de cambio de usos del suelo. ¿qué ha pasado en los terrenos urbanos?, ¿y en los rurales o forestales?

