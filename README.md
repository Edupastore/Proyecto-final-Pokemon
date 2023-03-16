# Proyecto-final-Pokemon

![pokemaniac](https://github.com/Edupastore/Proyecto-final-Pokemon/blob/main/pokemaniac.jpg)

## ⛓️ Índice de contenidos

1.[✍️ Descripción del proyecto](#descripción)\
2.[✌️ Motivación](#motivación)\
3.[📈 Extracción de datos](#extracción)\
4.[🧬 Transformación](#transformación)\
5.[🔎 Objetivo](#objetivo)
6.[📊 Estudio](#estudio)
7.[🤓 Conclusiones](#objetivo)
8.[👣 Siguientes pasos](#siguientespasos)

## ✍️ Descripción

Para la realización de este proyecto final, hemos recuperado parte de un proyecto que hicimos con anterioridad cuando llevamos a cabo una ETL (Extraction-Transformation-Loading). En este caso, nos hemos centrado en las dos primeras partes, las de extracción y transformación, para ampliar y mejorar nuestro conjunto de datos.

En cuanto a estos datos, la temática escogida ha sido Pokémon; concretamente hemos extraído datos sobre todos los Pokémon conocidos hasta la fecha (1.010) accediendo a diversas fuentes mediante diferentes métodos y hemos estandarizado y optimizado la información para que resultase más accesible.

A continuación, expondremos los motivos que nos han llevado a realizar este estudio, después se indicarán las técnicas empleadas para la recopilación y modificación de los datos y, una vez hecho esto, explicaremos cuál es el objetivo del tratamiento de estos datos y llevaremos a cabo un estudio estadístico mediante el cuál esperamos extraer una serie de conclusiones.

Para finalizar, se expondran unas líneas generales sobre los próximos pasos a dar para seguir nutriendo este proyecto y dotarlo de una mayor envergadura ofreciéndonos todo tipo de información que pueda resultar de utilidad a cualquier fan de Pokémon.

<a name="motivación"/>
 
## ✌️ Motivación

La motivación para la realización de este proyecto viene determinada por varias razones:

- Nostalgia: Pokémon es un franquicia longeva, con casi 30 años de vida y eso es algo que puede tener un significado bastante especial para las personas nacidas a finales de los 80 y principios de los 90, que vivieron el fenómeno Pokémon desde su génesis (como la persona que escribe estas líneas, que lleva jugando a los videojuegos de la saga principal desde hace casi 25 años). Hablar de Pokémon, es sinónimo de adolescencia y de amistad (necesitabas reunirte físicamente con tus amigos para intercambiar a estos "monstruos de bolsillo").

- Curiosidad: existe una cantidad ingente de datos en multitud de sitios Web. Como futuros analistas de datos, esto ofrece un abanico de posibilidades para poner en práctica las herramientas y tecnologías aprendidas y poder intentar ver más allá de dichos datos; observar si determinados datos tienen alguna historia interesante que contarnos, pero que a simple vista no puede apreciarse.

- Alcance: Pokémon es, a nivel mundial, la franquicia de medios más valiosa del mundo en términos de ingresos totales (según Statista, un portal alemán de estadística), por lo que la magnitud de este fenómeno invita a estudiarlo a fondo.
<br>

![pokevaluable](https://github.com/Edupastore/Proyecto-final-Pokemon/blob/main/pokevaluable.jpg)


<a name="extracción"/>
 
## 📈 Extracción de datos

Para recopilar los datos sobre todas las criaturas conocidas hasta la fecha, hemos acudido a varias fuentes de información empleando diferentes métodos según las necesidades que iban surgiendo en cada momento.

Los métodos utilizados para acceder, extraer y, finalmente, almacenar estos datos han sido:

- Web scraping: hemos extraído datos de diversas páginas que nos han ayudado a configurar nuestro conjunto de datos.
- Llamadas a la PokéAPI: la API principal de Pokémon; de aquí también hemos sacado información bastante valiosa para nuestro posterior estudio.

A continuación, vamos a citar todas las fuentes de las que hemos extraído datos y a detallar qué información hemos sacado de cada una.

<details>
<summary>Dataset de los primeros 898 Pokémon (gen. I a VIII)</summary>

<br>
El enlace al mencionado dataset es el siguiente: https://data.world/data-society/pokemon-with-stats
<br>
De este archivo csv hemos extraído valiosa información sobre los Pokémon que van desde la primera generación a la octava (correspondientes a las regiones de Kanto, Johto, Hoenn, Sinnoh, Teselia, Kalos, Alola y Galar).
<br>
EL fichero nos ha brindado la siguiente información: número de la Pokédex nacional, nombre del Pokémon, tipo 1, tipo 2, suma del total de las estadísticas, nivel de salud, ataque, defensa, ataque especial, defensa especial, velocidad, generación y si es legendario o no el Pokémon.
</details>

<details>
<summary>Web scraping del portal serebii.net</summary>
<br>
El enlace a la mencionada Web es el siguiente: https://www.serebii.net/pokemon/all.shtml
<br>
De esta página hemos tratado de extraer la misma información que arriba, pero de los Pokémon correspondientes a la novena generación, incluidos los dos últimos Pokémon anunciados recientemente (finales de febrero de 2023: Walking Wake y Iron Leaves).
<br>
A través del web-scraping y, mediante Selenium, hemos extraído parte de esa información sobre Pokémon de las regiones de Hisui (octava generación) y de Paldea (novena generación).
<br>
Este portal nos ha brindado la siguiente información: número de la Pokédex nacional, nombre del Pokémon, nivel de salud, ataque, defensa, ataque especial, defensa especial y velocidad.
</details>

<details>
<summary>Web scraping del portal pokemondb.net</summary>
<br>
El enlace a la mencionada página es el siguiente: https://pokemondb.net/pokedex/national#gen-9
<br>
En esta Web, hemos tratado de completar la información faltante sobre los Pokémon de Hisui y Paldea que mencionábamos en el epígrafe anterior.
<br>
Para ello, hemos vuelto a emplear Selenium y hemos extraído la información sobre los tipos de cada Pokémon. El resto de información faltante, la hemos calculado o la hemos rellenado de la forma más oportuna.
</details>

<details>
<summary>Web scraping del portal wikidex.net</summary>
<br>
El enlace a la mencionada página es el siguiente: https://www.wikidex.net/wiki/Lista_de_Pok%C3%A9mon_con_los_puntos_de_esfuerzo_que_dan_en_combate
<br>
De esta Web, hemos extraído datos sobre la experiencia base de cada Pokémon. Para sacar la información de los dos últimos Pokémon, hemos recurrido a otra página que contuviera esa información y hemos metido "a mano" esos datos. Una vez más, hemos vuelto a emplear Selenium para ello.
</details>

<details>
<summary>Web scraping del portal bulbapedia.bulbagarden.net/</summary>
<br>
El enlace a la mencionada página es el siguiente: https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_Egg_Group
<br>
De aquí, hemos extraído información sobre los grupos huevo de cada Pokémon (información importante para la crianza de Pokémon). Mediante el empleo de Selenium, hemos sacado los datos del grupo huevo 1 y del grupo huevo 2 de todos los Pokémon.
</details>

<details>
<summary>PokéAPI: pokeapi.co</summary>
<br>
El enlace a la mencionada API es el siguiente: https://pokeapi.co/
<br>
En esta Web, hemos tratado de completar la información faltante sobre los Pokémon de Hisui y Paldea que mencionábamos en el epígrafe anterior.
<br>
Para ello, hemos vuelto a emplear Selenium y hemos extraído la información sobre los tipos de cada Pokémon. El resto de información faltante, la hemos calculado o la hemos rellenado de la forma más oportuna.
</details>

<a name="transformación"/>

## 🧬 Transformación

El proceso de transformación ha sido, sin duda, el más tedioso y largo. Para no extendernos mucho, dejaremos a continuación una serie de pinceladas, unas líneas generales, sobre lo que hemos hecho.
<br>
    - En primer lugar, hemos limpiado los datos del primer dataset, llevando a cabo la eliminación de registros con el mismo número de Pokémon (eran distintas versiones del mismo, no Pokémon completamente distintos), la homogeneización de los datos contenidos en cada columna, hemos cambiado el formato del número de la Pokédex (de 1, 2 , 3, etcétera hemos pasado a 0001, 0002, 0003, etcétera), hemos cambiando en "legendary" los booleanos True/False por "leg"/"notleg", en "type2" hemos rellenado con "Mono" los valores nulos (para indicar que son Pokémon monotipo) y, en definitiva, hemos comprobado de manera exhaustiva que todo concordase y tuviese coherencia.
<br>
    - En segundo lugar, hemos transformado también los datos obtenidos de los dos portales Web mencionados con anterioridad y los hemos "acondicionado" de tal manera que el producto final fuese una tabla de idénticas dimensiones, con idénticos nombres de columnas e idénticos tipos de datos que los del dataset anterior. Tras una serie de transformaciones, lo conseguimos.
<br>
    - En tercer lugar, hemos comprobado que los tipos de datos del primer dataset y del segundo fuesen iguales y hemos optimizado dichos tipos.
<br>
    - Por último, hemos concatenado ambas tablas para conformar un registro único con datos sobre todos los Pokémon existentes a fecha de hoy (13/02/2023).
<br>

<a name="carga"/>

## 🧬 Carga en base de datos
El último paso ha sido la incorporación de esta tabla maestra a una base de datos en SQL. Para ello, hemos creado en Workbench el esquema de la base de datos (configurando la tabla de Pokémon, con sus columnas y los tipos de datos de cada una de ellas).
<br>
Una vez hecho esto, hemos volcado los datos de nuestra tabla maestra en la base de datos que hemos llamado "pokemon". Con esta acción, hemos dado por concluída la elaboración del proyecto.
<br>

![eerd](https://github.com/Edupastore/w4-ETL-Project/blob/main/eerd.jpg)
<br>

<a name="objetivo"/>

## 📊 Objetivo
El objetivo que nos hemos marcado con este proyecto ha sido configurar una base de datos completa sobre todos los Pokémon existentes, para que nos pueda servir como herramienta de consulta (por ejemplo, cuando estemos jugando a cualquiera de los juegos principales de la franquicia).
<br>

![sqlpoke](https://github.com/Edupastore/w4-ETL-Project/blob/main/sqlpoke.jpg)
<br>