---
layout: article-v3
title: Las Conclusiones de la CVR en formato JSON
lang: es
type: article
excerpt: Convertimos las 171 Conclusiones del Informe Final de la CVR a un formato JSON, para que puedan ser importadas fácilmente a nuevas experiencias digitales.
tags: [cvr, informe final, derechos humanos, analisis computacional, peru, conclusiones, json, regex]
permalink: conclusiones-cvr-json/
author: Eduardo Marisca
---
Hace unos días compartí <a href="http://marisca.pe/adaptando-informe-final-cvr-mundo-digital/">un poco del trabajo que he estado haciendo para convertir el Informe Final de la CVR en un documento más amigable al mundo digital</a> -- un trabajo que en sí construye sobre <a href="http://www.mutaciones.pe/2013/05/13/una-lectura-computacional-del-informe-final-de-la-cvr/">un primer esfuerzo hace unos años experimentando con el texto del informe y análisis del lenguaje natural</a>. Ahora he querido trabajar un poco más en detalle con una sección en particular: las Conclusiones, que representan un resumen general del informe y brindan un panorama sumamente completo de las causas, desarrollo y consecuencias de la violencia interna en el Perú de los últimos años.

El informe tiene 171 conclusiones generales cuya lectura es una gran introducción a su contenido general -- de lectura obligatoria para cualquier estudiante de Realidad Social Peruana en Estudios Generales Letras en la PUCP. Por lo mismo, creo que tienen un enorme potencial: son una tajada del informe mucho más fácil de enfrentar, pero que al mismo tiempo tiene un impacto enorme. Incluso si no piensas leer nada más de su contenido, al menos leer las Conclusiones te dejará en una posición mucho mejor informada sobre el trabajo realizado por la Comisión y una comprensión mucho más clara de la historia peruana reciente.

Siempre he querido trabajar en una versión más interactiva de las Conclusiones, una presentación digital que pudiera combinar un buen diseño con material multimedia para amplificar su impacto y servir como un punto de partida a una reflexión informada. Con las debidas referencias cruzadas, además, las Conclusiones pueden convertirse más en la entrada a un contenido mucho más rico y completo. Pero del mismo modo que con el resto del informe, las Conclusiones no están disponibles en un formato digital nativo: el documento oficial las incluye únicamente como un formato PDF con el cual es difícil trabajar. Para poder tomar las Conclusiones como una fuente de datos, primero era necesario realizar un proceso de limpieza del contenido.

Este proceso empezó a partir de <a href="https://github.com/piscosour/mem0r1a/blob/master/prototypes/conclusiones/conclusiones.txt">una versión en formato de texto de las Conclusiones</a>. Sobre este formato, desprovisto de toda decoración o diagramado, fue posible utilizar un pequeño programa en Python para empezar a limpiar y ordenar la data. Las Conclusiones tienen una estructura bastante regular: las secciones empiezan con números romanos, las subsecciones con letras y cada conclusión está numerada. Utilizando <a href="http://regexone.com/">expresiones regulares</a>, el programa analiza el inicio de cada línea del archivo para determinar su naturaleza, y luego crea un objeto para cada conclusión incluyendo su número, su contenido, y la sección y subsección a la que pertenece.

<div class="article-image_container">
	<a href="/files/img/cvr-conclusiones-regex.jpg"><img alt="Utilizando expresiones regulares, determinamos la naturaleza de cada una de las líneas del archivo." src="/files/img/cvr-conclusiones-regex.jpg" class="article-image" /></a>
	<p>Utilizando expresiones regulares, determinamos la naturaleza de cada una de las líneas del archivo.</p>
</div>

Con estos objetos, creamos un diccionario que contiene la totalidad de las conclusiones y sus atributos. Con este diccionario podríamos empezar ya a servir contenido directamente a un formato interactivo, por ejemplo utilizando un framework web como Flask. Por ahora, quiero solamente convertir este diccionario, que es un objeto nativo de Python, a un formato más universal como JSON. JSON es un formato sumamente común a través de la web, una forma de representar objetos de tal manera que pueden ser importados desde muchísimos lenguajes de programación, frameworks y bases de datos, convirtiéndolo en un formato ideal para compartir datos de manera que sean interoperables entre muchos sistemas.

Utilizando la capacidad nativa de Python para codificar JSON, convertimos el diccionario en un archivo que contiene todas las conclusiones y sus atributos representados en este formato:

<div class="article-image_container">
	<a href="/files/img/cvr-conclusiones-dictionary.jpg"><img alt="Convirtiendo un diccionario de Python en un archivo codificado en JSON." src="/files/img/cvr-conclusiones-dictionary.jpg" class="article-image" /></a>
	<p>Convirtiendo un diccionario de Python en un archivo codificado en JSON.</p>
</div>

El resultado es <a href="https://github.com/piscosour/mem0r1a/blob/master/prototypes/conclusiones/cvr_conclusiones.json">un archivo sumamente ligero y portátil que puede ser importado virtualmente desde cualquier entorno de desarrollo, y que contiene las 171 conclusiones con sus atributos principales</a>. Cualquier persona interesada en construir versiones interactivas de este contenido puede utilizar esta data limpia para alimentar su propia base de datos y crear todo tipo de interacciones inteligentes.

<div class="article-image_container">
	<a href="/files/img/cvr-conclusiones-json.jpg"><img alt="Una muestra de las conclusiones como objetos JSON." src="/files/img/cvr-conclusiones-json.jpg" class="article-image" /></a>
	<p>Una muestra de las conclusiones como objetos JSON.</p>
</div>

Este era un primer paso necesario para las siguientes cosas que quiero hacer: tomando estos objetos en JSON -- básicamente la data limpia -- quiero alimentar una base de datos que luego pueda estar disponible públicamente a través de una API, para que cualquier persona pueda acceder a esta información fácilmente. Eso, sin embargo, va a tomar un poco más de trabajo -- así que mientras tanto quería ir compartiendo la fuente de datos por si a alguien le pueda ser útil. Tanto la data limpia como la fuente original, así como el código utilizado para hacer la limpieza, <a href="https://github.com/piscosour/mem0r1a/tree/master/prototypes/conclusiones">están disponibles libremente en GitHub para cualquiera que quiera jugar con ellos</a>.
