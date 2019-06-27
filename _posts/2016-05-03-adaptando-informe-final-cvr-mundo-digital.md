---
layout: article-v3
title: Adaptando el Informe Final de la CVR al mundo digital
lang: es
type: article
excerpt: El Informe Final de la CVR no nació como un documento digital. Esta colección de PDFs reordenados y renombrados son un primer paso hacia la construcción de un documento nativo digital.
tags: [cvr, informe final, derechos humanos, analisis computacional, peru]
permalink: adaptando-informe-final-cvr-mundo-digital/
author: Eduardo Marisca
---
El <a href="http://www.cverdad.org.pe/ifinal/index.php">Informe Final de la Comisión de la Verdad y la Reconciliación</a>, finalizado y publicado el 2003, no fue pensado como un documento digital. El documento abarca nueve tomos con cientos de secciones y capítulos con el que es quizás el análisis más pormenorizado de la historia peruana reciente. Por lo mismo, es sumamente difícil de navegar y consumir: un documento tan grande y ambicioso, que presenta una invitación importantísima a la reflexión sobre la historia y la discusión sobre nuestros problemas como nación, representa un desafío enorme.

<div class="article-image_container">
	<a href="/files/img/entrega-cvr.jpg"><img alt="Entrega del Informe Final de la CVR en el año 2003. Fuente: IDEHPUCP." src="/files/img/entrega-cvr.jpg" class="article-image" /></a>
	<p>Entrega del Informe Final de la CVR en el año 2003. Fuente: IDEHPUCP.</p>
</div>

Desde su publicación original, la CVR hizo disponible el contenido total del Informe Final -- que además es contenido de dominio público -- <a href="http://www.cverdad.org.pe/">a través de su sitio web</a>, como una serie de PDFs de las diferentes secciones y capítulos. Pero, de nuevo, el informe no nació como un documento digital: incluso en la tabla de contenidos en el sitio web, los archivos están separados por su distribución a lo largo de los nueve tomos, en lugar de formar un documento continuo e integrado.

Hace tiempo que <a href="http://marisca.pe/projects/mem0r1a/">quiero utilizar el informe como la base de un análisis computacional</a> -- pensar en qué ocurre cuando hacemos que una computadora lea el informe y nos pueda dar respuestas sobre su contenido. Pero eso requiere de todo un trabajo de preparación del contenido para que una computadora pueda leerlo: hasta donde he podido buscar, el informe no se encuentra disponible en formato de texto o HTML que haga más fácil su lectura computacional. Y al empezar a recopilar los documentos PDF disponibles, me di cuenta que estaban desordenados, con nombres inconsistentes y sin una estructura orgánica.

Así que he empezado el trabajo de convertir el informe en un documento digital. El primer paso ha sido ordenar la colección de documentos PDF de manera que sean más fáciles de navegar: eliminando la estructuración por tomos y reordenando los archivos según una estructura de carpetas que refleja la tabla de contenidos.

Pero quizás lo más importante sea renombrar todos los archivos. Para darles una estructura más sistemática, cada archivo PDF dentro de la colección original en el sitio del a CVR ha sido renombrado de tal manera que indique claramente su lugar en el documento. El nombre de cada archivo empieza ahora con una notación numérica indicando de qué parte, sección o capítulo se trata, seguido del título real del contenido para facilitar su lectura y navegación. Un <a href="https://github.com/piscosour/mem0r1a/blob/master/informe_pdf/informe_pdf_mapa.txt">mapa general de contenidos</a> -- una versión actualizada de la tabla de contenidos del original -- captura toda esta estructura y refleja las dependencias que existen entre los archivos:

<pre>
INFORME FINAL

[Parte]_[Sección]_[Capítulo]_[Subcapítulo]_

00_Preliminares

	00_01_Portada
	00_02_Firmas

01_EL PROCESO, LOS HECHOS, LAS VÍCTIMAS

	01_00_01_Prefacio
	01_00_02_Introducción
	01_01_Exposición general del proceso
		01_01_01_Los períodos de la violencia
		01_01_02_El despliegue regional
		01_01_03_Los rostros y perfiles de la violencia
		01_01_04_La dimensión jurídica de los hechos
</pre>

Siguiendo esta notación, cualquier lector/investigador pueden utilizar la codificación para referir a un lugar específico del informe sin depender de la paginación de una edición impresa específica. Esto hace que la referenciación interna sea más fácil de realizar y que se pueda mantener consistencia entre versiones digitales e impresas del documento.

Es interesante lo que uno descubre en el proceso: por ejemplo, que en algunos casos no todos los PDFs originales estaban disponibles, o que la versión incluida en el sitio web no es exactamente igual a la versión que fue finalmente impresa (cuyos PDFs, a su vez, <a href="https://sites.google.com/a/pucp.pe/informe-final-de-la-cvr--peru/">pueden encontrarse también en línea</a>). Existen <a href="http://idehpucp.pucp.edu.pe/tipo/informe-final/">varios</a> <a href="http://www.derechos.org/nizkor/peru/libros/cv/">repositorios</a> en la web que albergan el mismo contenido, pero no todos son completamente consistentes entre sí. Esto fue especialmente cierto respecto a los anexos finales -- nueve según el sitio web, pero doce según la versión impresa. Para esta edición digital tuve que ensamblar una combinación de ambos, de tal manera que no se pierda nada del contenido.

<a href="https://github.com/piscosour/mem0r1a/tree/master/informe_pdf">Toda esta estructura y todos los archivos reordenados y renombrados están disponibles en un repositorio en GitHub</a>. Este es el primer paso para volver el Informe Final un documento nativo digital: ahora que la data original está ordenada, el siguiente paso es convertir los archivos codificados en PDF en un formato más amigable para el análisis computacional, como el texto simple. Esto luego puede utilizarse para reconstruir una versión interactiva del documento, que soporte vínculos entre los elementos del texto y diferentes medios y contenidos incrustados. Finalmente, una vez que la data esté limpia y procesada, el contenido del informe se convierte en una gran base de datos sobre la cual podemos desarrollar todo tipo de aplicaciones interactivas -- pero esto solo es posible si una computadora puede leer el contenido.

Mientras tanto, quiero compartir este primer paso para ahorrarle a cualquier persona interesada el trabajo de recopilar todos estos archivos y darles una estructura. Esta primera versión en PDF debería ser más fácil de trabajar y manipular que la versión existente en el sitio web de la CVR, y también más fácil de reproducir y modificar, así que con suerte puede ser una herramienta útil para el trabajo de investigadores que quieran explorar este contenido en formato digital.