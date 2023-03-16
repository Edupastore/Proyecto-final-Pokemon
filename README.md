# Proyecto-final-Pokemon

![pokemaniac](https://github.com/Edupastore/Proyecto-final-Pokemon/blob/main/pokemaniac.jpg)

## ⛓️ Índice de contenidos

1.[✍️ Descripción del proyecto](#descripción)\
2.[✌️ Motivación](#motivación)\
3.[📈 Extracción de datos](#extracción)\
4.[🧬 Transformación](#transformación)\
5.[🔎 Objetivo](#objetivo)
6.[📊 Estudio](#estudio)
7.[🤓 Conclusiones](#conclusiones)
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
Esta herramienta, nos brinda muchísima información acerca del mundo Pokémon. Cabe comentar, que en algunos casos la información que intentábamos extraer no estaba completa y que sólo estaba disponible hasta una determinada generación. En algunos casos, hemos podido subsanar esta situación, pero en otros no, descartando incorporar esa información a nuestro conjunto de datos.
<br>
Los datos extraídos a través de llamadas a la PokéAPI son los que se enumeran a continuación: categoría del Pokémon (si es inicial, bebé, fósil, legendario, singular o normal), altura, peso, color, género, ciclos para eclosionar huevos, ratio de captura, felicidad base, ratio de crecimiento y experiencia acumulada en el nivel 100.
</details>

Toda esta parte de extracción y la posterior de transformación, las hemos llevado a cabo a través de la utilización de un Jupyter Notebook llamado "Pokemones.ipynb" (alojado en la carpeta src del repositorio).

<a name="transformación"/>

## 🧬 Transformación

El proceso de transformación ha sido uno de los pasos más densos de este proyecto. Para no extendernos mucho, indicaremos a continuación las líneas generales sobre las transformaciones que hemos ido implementando conforme íbamos recopilando la información:
<br>
- Hemos limpiado los datos conforme los hemos ido obteniendo siguiendo una serie de pasos para ello. Hemos llevado a cabo la eliminación de registros que no nos hacían falta, hemos comprobado valores nulos y los hemos rellenado cuando ha sido oportuno y hemos comprobado que no hubiese registros duplicados.
<br>
- También hemos tratado de homogeneizar los datos de algunas columnas para que todo tuviese un sentido, una coherencia y de cara a facilitar el análisis posterior de los datos.
<br>
- No hemos analizado si había datos atípicos, porque todos los datos de nuestro conjunto (Pokémon) tienen sentido para permanecer en el dataset. Tampoco hemos comprobado correlaciones ni colinealidad en este apartado porque no nos ha interesado; las columnas se han elegido con total discrecionalidad y sin importar si eran dependientes unas de otras.
<br>
- Hemos creado nuevas variables (columnas) que son combinación lineal de otras columnas o transformaciones de las mismas. También hemos eliminado columnas que no nos servían para el estudio y añadido otras.
<br>
- Además, hemos comprobado que los tipos de datos de nuestro primer dataset (generaciones I a VIII) y del segundo (generación IX) fuesen iguales y hemos optimizado dichos tipos para que ocupasen lo mínimo posible en memoria.
<br>
- Para finalizar, hemos concatenado ambos conjuntos de datos para conformar un registro único con información relevante sobre todos los Pokémon existentes a fecha actual (16/03/2023) y para un posterior análisis estadístico que veremos en los próximos epígrafes.
<br>
Los datos resultantes se han exportado a un fichero con extensión csv bajo el nombre de "pokefinal.csv" (alojado en la carpeta data del repositorio).

<a name="objetivo"/>

## 🔎 Objetivo

Una vez configurado el conjunto de datos a nuestra medida, hemos pasado a realizar un estudio con el objetivo de ver si existen diferencias significativas entre las distintas generaciones Pokémon y, de haberlas, tratar de encontrar los pares de generaciones entre los que las hay.
<br>
Este objetivo, ha sido posible llevarlo a cabo gracias a diversas técnicas estadísticas (fundamentalmente tests) que veremos con más profundidad en el siguiente apartado.
<br>
Por último, cabe comentar que hemos llevado a cabo este análisis sobre si existen diferencias significativas estudiando todas las variables de nuestro conjunto de datos (tanto las numéricas como las categóricas).

<a name="estudio"/>

## 📊 Estudio

Para llevar a cabo nuestro estudio, hemos utilizado dos herramientas principales, varias auxiliares que nos han ayudado a determinar cuál de las principales era más conveniente utilizar para cada variable y una prueba post hoc para ayudarnos a determinar en qué pares de muestras hay diferencias significativas.

Las dos herramientas principales que hemos empleado son:

- Test de ANOVA: se trata de una técnica estadística que se utiliza para comparar la media de tres o más grupos (generaciones en nuestro caso). En términos generales, se utiliza para determinar si hay diferencias significativas entre las medias de tres o más grupos. Para llevar a cabo ANOVA, se tienen que cumplir tres supuestos que son: normalidad, homocedasticidad e indepedencia de las muestras. Si no se cumplen estos supuestos, se procede con la otra técnica.

- Prueba de Kruskal-Wallis: es un test no paramétrico menos potente que ANOVA, que se puede utilizar para comparar la mediana de tres o más grupos independientes, aunque las muestras no cumplan con los supuestos que se indicaron antes para llevar a cabo ANOVA.

Las herramientas auxiliares para determinar si usar ANOVA o Kruskal-Wallis son estas:

- Test de Shapiro: es una prueba estadística utilizada para determinar si un conjunto de datos sigue una distribución normal o no.

- Test de Levenne: es una prueba que nos ayuda a determinar si existe homocedasticidad entre las muestras, es decir, que este test nos sirve para evaluar si las varianzas nuestros grupos son iguales o no.

- Test de independencia de muestras y gráfico de dispersión: el test de independencia es una prueba estadística utilizada para verificar si las muestras de datos son independientes entre sí o no, mientras que el gráfico de dispersión es una herramienta visual de apoyo para ver si existen o no patrones que determinen si hay relaciones de dependencia o no entre las muestras.

La prueba post-hoc que hemos utilizado es la siguiente:

- Prueba de Tukey: es una prueba post-hoc que se utiliza después de realizar una prueba de comparación de múltiples grupos, para determinar cuáles de las muestras tienen diferencias significativas entre sí. La prueba de Tukey se utiliza para comparar todas las posibles combinaciones de pares de grupos. Es una prueba conservadora, lo que significa que es menos propensa a cometer errores de tipo I (rechazar la hipótesis nula cuando es verdadera) que otras pruebas, por ello nos decantamos por el empleo de este test.

El procedimiento que hemos llevado a cabo para el estudio de cada variable entre las distintas generaciones Pokémon para ver si existían diferencias significativas ha sido el siguiente:

1º. Hemos pasado los tests para verificar si se cumplen o no los supuestos de normalidad, homocedasticidad e independencia de muestras para saber si pasar posteriormente prueba de ANOVA o Kruskal-Wallis.

2º. Para el test de normalidad (Shapiro), en el caso de que alguno de los p-valor haya sido menor que el nivel de significatividad (0.05, ya que asumimos un nivel de confianza del 95%), entonces hemos rechazado la hipótesis nula de que los datos siguen una distribución normal.

3º Si los otros dos supuestos sí se han cumplido, hemos normalizado los datos (a pesar de que, en ocasiones, puede ser contraproducente) y hemos pasado test de Anova.

4º Si uno de los otros dos supuestos o ninguno de los dos se ha cumplido, hemos pasado la prueba de Kruskal-Wallis.

5º Para las variables categóricas hemos llevado a cabo una codificación numérica en primera instancia y luego hemos pasado ANOVA si se cumplía el supuesto de independencia de muestras (los otros dos no eran necesarios con este tipo de variables) o Kruskal-Wallis si no se cumplía dicho supuesto.

6º Por último, si al pasar bien el test de ANOVA, bien el de Kruskal-Wallis, hemos recibido como respuesta que hay evidencia significativa para rechazar la hipótesis nula de que las muestras tienen la misma media/mediana poblacional, hemos pasado la prueba de Tukey para ver entre qué pares de muestras existen diferencias significativas en cuanto a la variable que le hayamos pasado a los diferentes tests.

Todo lo que hemos ido analizando en este estudio, se ha llevado a cabo en un Jupyter Notebook llamado "Estudio.ipynb" (alojado en la carpeta src del repositorio).

<a name="conclusiones"/>

## 🤓 Conclusiones

Las conclusiones a las que hemos llegado tras la realización de este estudio estadístico son:

- Por un lado, que las variables numéricas correspondientes a las estadísticas de los Pokémon, al rol competitivo potencial de cada Pokémon (ANOVA) y a los datos de altura y peso (Kruskal-Wallis) siguen una distribución similar entre generaciones, ya que no podemos rechazar la hipótesis nula de que las muestras tienen la misma media/mediana poblacional. Podemos decir en este sentido, por ejemplo, que no se han potenciado ni "nerfeado" en términos medios las estadísticas de los Pokémon con el paso de las generaciones.

- Para las variables categóricas category y color (Kruskal-Wallis), tampoco podemos rechazar la hipótesis nula de que las muestras tienen la misma mediana poblacional, por lo que podemos intuir que las proporciones de tipos de Pokémon en cuanto a si son normales, legendarios, fósiles, etcétera, entre generaciones, responden a cierta similitud.

- Por otro lado, las variables numéricas hatch, capt_rate, base_happ y base_exp, y las variables categóricas growth_rate, type1, type2, gender, egg_gr1 y egg_gr22 (Kruskal-Wallis) nos muestran que existen diferencias significativas entre diferentes pares de generaciones. Habría que hacer un estudio más a fondo para ver a qué se deben estas diferencias.


<a name="siguientespasos"/>

## 👣 Siguientes pasos

Con intención de potenciar el proyecto y dotarlo de mayor información, los próximos pasos a seguir podrían ser los siguientes:

- Efectuar un análisis estadístico aún más riguroso y exhaustivo que el ya realizado para ver si se puede extraer información más específica sobre esas diferencias significativas entre muestras (generaciones) que hemos obtenido en el estudio actual.

- Recopilación de datos que nos proporcionen información más detallada sobre cada Pokémon (fortalezas, debilidades, habilidades, ataques que puede aprender, objetos que se le pueden equipar, puntos de esfuerzo (EV's) que proporciona al derrotarlo, juegos de la saga principal en los que aparece y un largo etcétera). Esto puede llevarse a cabo a través de la PokéAPI y del scrapeo de diferentes sitios Web.

- De forma paralela, sería interesante llamar a la API de Pokémon Go y extraer todos los datos relevantes de la aplicación para elaborar una tabla maestra que nos pueda ser de utilidad en un futuro (por ejemplo, para saber a golpe de click qué Pokémon son los mejores para acometer una incursión contra cierto legendario).
