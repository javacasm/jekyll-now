--- 

title: Montando un blog con jekyll
layout: post
status: publish
published: true
categories: []

tags: []

comments: []

---

Cansado de tantos problemas de rendimiento y mantenimiento de wordpress he decidido migrar a un sistema más sencillo de mantener y sobre todo rápido, sin depender de infraestructura, con vistas a poder user un hosting doméstico (sí en casa, que 100Mb de subida dan para mucho :) )

Veamos los pasos

* Instalar **jekyll**. Ya hemos hablado de cómo hacer en [este post de elcacharreo](http://blog.elcacharreo.com/2014/02/10/sistema-de-publicacion-de-paginas-estaticas/)

* Extraer la información de wordpress. Jekyll tiene una [página](http://import.jekyllrb.com/docs/home/) destinada a estos temas y en concreto una para [wordpres](http://import.jekyllrb.com/docs/wordpress/). Tenemos que tener operativo ruby y tener instaladas algunas gemas pero dado que ya habíamos instalado jekyll debemos tenerlo todo listo. 
	La importación no puede ser mas sencilla: personalizamos para nuestra configuración (esencialmente sobre la base de datos) y ejecutamos, obteniendo  un directorio **_posts** donde se genera un fichero MarkDown por cada post. 
	En mi caso como tenía un plugin de foros en wordpress existen algunos posts que hay que evitar que se vean, que son los que contienen la información de los foros. Sólo hay que marcar la etiqueta **published** a _false_ y listo.

* Copiamos el contenido de la carpeta **_posts** a la instalación de jekyll y generamos la estructura del bloq con 

		jekyll build

	Tras lo cual tendremos una carpeta _site que será el blog propiamente.

* Retocamos la configuración de los layout (en la carpeta **_layout**) y del blog en **_cfb.yml**.

* Para facilitar la publicación desde mi máquina, o desde cualquier otra, he creado un repositorio github con el contenido del blog. De esta manera puedo actualizar fácilmente desde cualquier sitio y tengo una copia de respaldo.

* Quedan pendientes algunos temas:
	* Ver como activar un hook en github para que regenere la estructura el sitio tras una actualización.
	* Actualizar los enlaces entre posts que no se modifican y seguiran apuntando al original.
	* En concreto, las imágenes que no descargan y que tendremos que descargar y enlazar a la nueva dirección.
	* Podemos trabajar las etiquetas (Tag) y categorías. Para ello podemos usar las [etiquetas de publicación de jekyll](http://import.jekyllrb.com/docs/wordpress/).
	* Añadir [widgets con las etiquetas](http://blog.meinside.pe.kr/Adding-tag-cloud-and-archives-page-to-Jekyll/) o los posts más visitados para completar el blog.

Podéis ver el resultado del [elCacharreo 2.0](http://static.elcacharreo.com) (muy espartano de momento)