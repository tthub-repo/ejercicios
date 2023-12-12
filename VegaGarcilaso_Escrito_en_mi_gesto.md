---
title: Ejercicio de codificación con VsCode 
layout: default
---

# Instalación de VS Code 

1. Descarga e instalación: <https://code.visualstudio.com/Download>

2. Configurar la lengua, buscando "Configure language", y elijan el idioma que quieran. 

3. Instalación del plugin [Scholarly XML](https://marketplace.visualstudio.com/items?itemName=raffazizzi.sxml), siguiendo [estos pasos](https://tthub.io/aprende/tutorial/edicion-digital-con-VS-code/edicion-digital-con-VS-code/scholarly_xml) en el tutorial. 

4. Intalar el plugin de [TEI Publisher](https://teipublisher.com/index.html), desde el programa [VS Code](https://marketplace.visualstudio.com/items?itemName=e-editiones.tei-publisher-vscode).


# Codificación poema "Escrito está en mi alma vuestro gesto"

Para este ejercicio codificaremos un soneto de Garcilaso de la Vega. Para ello, utilizaremos el texto disponible en la [Biblioteca Virtual Miguel de Cervantes](https://www.cervantesvirtual.com/obra-visor/sonetos--27/html/000fe41e-82b2-11df-acc7-002185ce6064_1.html#PV_5_):

Los pasos a seguir son los siguientes:  

**[Paso 1]** Cread un documento XML-TEI (con el programa VsCode). 

**[Paso 2]** Utilizad como declaración un esquema TEI All y copiad esta plantilla: 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="http://www.tei-c.org/release/xml/tei/custom/schema/relaxng/tei_all.rng" type="application/xml" schematypens="http://relaxng.org/ns/structure/1.0"?>
<TEI xmlns="http://www.tei-c.org/ns/1.0">
  <teiHeader>
      <fileDesc>
         <titleStmt>
            <title>Title</title>
         </titleStmt>
         <publicationStmt>
            <p>Publication Information</p>
         </publicationStmt>
         <sourceDesc>
            <p>Information about the source</p>
         </sourceDesc>
      </fileDesc>
  </teiHeader>
  <text>
      <body>
         <p>Some text here.</p>
      </body>
  </text>
</TEI>
```

**[Paso 3]** En el elemento `<teiHeader>` tendréis que completar las siguientes informaciones:

- [`<title>`](https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-title.html): título de vuestro archivo digital (algo como "Codificación de un poema de Garcilaso de la Vega" por ejemplo.
- [`<author>`](https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-author.html): irá vuestro nombre
- [`<publicationStmt>`](https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-publicationStmt.html): las informaciones donde se ha realizado la codificación del archivo.  
- [`<sourceDesc>`](https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-sourceDesc.html): la fuente original en la que se basará vuestra edición. Para ello, sugiero que utilices el siguiente esquema:

```xml
<bibl>
	<author></author>
	<title></title>
	<pubPlace></pubPlace>
	<publisher></publisher>
	<date></date>
	<biblScope></biblScope>
</bibl>
```

**[Paso 3]** En el cuerpo del documento `text > body` debéis codificar el texto. Para facilitaros el ejercicio, aquí tenéis una transcripción fiel:

```txt
Escrito está en mi alma vuestro gesto, 		
y cuanto yo escribir de vos deseo; 		
vos sola lo escribiste, yo lo leo 		
tan solo, que aun de vos me guardo de esto. 		

En esto estoy y estaré siempre puesto, 	  	
que aunque no cabe en mí cuanto en vos veo, 		
de tanto bien lo que no entiendo creo, 		
tomando ya la fe por presupuesto. 		

Yo no nací sino para quereros; 		
mi alma os ha cortado a su medida: 	 	
por hábito del alma misma os quiero. 		

Cuanto tengo confieso yo deberos; 		
por vos nací, por vos tengo la vida, 		
por vos he de morir y por vos muero.
```

Vuestra misión será codificar los siguientes elementos:

- `<head>`: el título del poema, si tiene
- `<lg>`: para todo el poema.
- `<lg>` : también para las estrofas
- `l`: para cada uno de los versos

Podéis también añadir atributos: 

- Podéis añadir los atributos a algunos de los elementos, por ejemplo: `<lg type="XXX" rhyme="XXXX">`
- Marcar la rima de los versos con el elemento `<rhyme>`.

Para los más atrevidos, también podéis regularizar el texto, señalando la lectura original y la regularización de la forma. Por ejemplo

```xml
<choice>
	<orig>deste</orig>
	<reg>de este</reg>
</choice>
```

**[Paso 4]** Lo ideal es que mientras vayáis codificando os aseguréis que vuestro documento está bien formado y es válido, para ello os ayuda el sistema que explciamos en el [ejercicio anterior](https://tthub.io/beta/aprende/ejercicios/creacion-de-un-documento-tei) (Pasos 4 y 5).

![FPG](https://github.com/tthub-repo/ejercicios/blob/master/img/5.FPG_Bordona_19.jpg?raw=true)

![FPG](https://github.com/tthub-repo/ejercicios/blob/master/img/5.FPG_Bordona_20.jpg?raw=true)
