# Documentación Para Crear Emails Dinámicos

## Historia del Correo Electrónico

El desarrollo de emails no ha cambiado en los últimos 25 años, su estructura esta compuesta de html y CSS inline.

Los emails no trabajan como una página web y visceversa, el auge de los dispositivos móviles a cambiado las técnicas de desarrollo para diferentes clientes de email, entre los más usados según estadísticas recogidas hechas por  la compañia Litmus se encuentran:

1. **Apple iPhone** 
2. **Gmail** 
3. **Apple iPad** 
4. **Apple Mail**
5. **Outlook** 
7. **Samsung Email App** 
8. **Google Android** 
9. **Yahoo! Mail** 
10. **Windows Mail** 

Para estar al tanto de las estadísticas de los provedores de internet visitar el siguiente [enlace](https://emailclientmarketshare.com/) 

## Entornos de Trabajo 

Para estructurar rápidamente tablas se recomienda usar el plugin de  [emmet](https://emmet.io/) e instalarlo en tu editor de código favorito.

###Ejemplos:

Crear una tabla con una columna y tres filas    
    <!-- table>tr(td*3) -->
    table>tr(td*3)  

    <table>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </table>    

Crear una tabla con tres columnas y tres filas
    
    <!-- table(tr(td*3)*3) -->
    table(tr(td*3)*3)   
    <table>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </table>

## Bases de Desarrollo Para Email

Conceptos básicos para desarrollar emails:

### Formatos de Imagen:

_GIF_
: Formato con algoritmo de compresión de datos perfecto para imagénes gráficas, su cantidad de colores es limitada (256) y sirve para mostrar animaciones.

_JPG_
: Usar imágenes de alta compresión, tanto en color como en escala de grises, con alta calidad.

_PNG_
: Permite las transparencias de mucha calidad, debido a su algoritmo de compresión sin perdida para bitmaps, por lo que no hay perdida de datos. 

### Comentarios en los emails:

Nos ayudan a comunicarnos y a trabajar en equipos

    <!-- Email Header -->

### Dispositivos Android:

La mayoría de problemas surgen de Android debido a la fragmentación de su código fuente. 

### Proovedores de Email:

Es en dónde se testean los emails y se basa en el público objetivo.

### Reglas de CSS para emails:

En el siguiente [enlace](https://www.campaignmonitor.com/css/) encontrarás que reglas **CSS3** funcionan en las diferentes clientes de email.

### Elementos HTML más usados:

A continuación una lista de los elementos más usados para el desarrollo de emails, la propiedad `colspan="2"` que une dos columnas debería no usarse debido a que el cliente Outlook no tiene el soporte para renderizarlo.

    <table>
        <tr>
            <td></td>
        </tr>
    </table>

    <span>Título</span>

    <div></div>

    <img src="" alt="">



## Buenas Prácticas en Plantillas de Estilos para email.

Existen algunas propiedades y hacks para que nuestros emails se adapten bien a casi todos los dispositivos y clientes de correo electrónico, a continuación una lista de hacks que nos sirven para realizar emails responsive.

### DOCTYPE

Se recomienda el siguiente doctype porque hay algunos clientes de correo que necesitan de esta propiedad para poder mostrar el email.

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml">

### Metatag Viewport
Meta etiqueta para que el browser interprete el tamaño del dispositivo y permita el uso de mediaqueries.

    <!-- view port meta tag -->
    <meta name="viewport" content="width=device-width, initial-scale=1">

### Hacks CSS head

##### Evitar que iPhone nos agrande las fuentes

    * {
        -webkit-text-size-adjust: none;
        -ms-text-size-adjust: none;
        max-height: 1000000px;
    }

##### Quitar el padding del Cliente Outlook para PC (2013) en los elementos `<a></a>` 

    #outlook a {
        padding: 0;
    }
##### Clases para clientes online como !Yahoo, Gmail o IOS.

    .ReadMsgBody {
        width: 100%;
    }
    .ExternalClass {
        width: 100%;
    }
    .ExternalClass * {
        line-height: 100%;
    }

##### Prevenir que los teléfonos IOS y Android conviertan las palabras que tengan alguna extensión de dominio ej: _hola.com_ en color azul con la línea característica de un enlace.

    .ios_geo a {
        color: #1c1c1c !important;
        text-decoration: none !important;
    }   

##### Media Queries

En el caso de las media queries se intenta cubrir la gran cantidad de dispositivos de acuerdo a los Clientes de Email en que se valla a usar el correo, en este caso se usa un breakpoint de **600px** para abaracar gran cantidad de dispositvos, esta medida _puede variar_  e incluso se pueden insertar más breakpoints dependiendo los resultados que querramos obtener, según los testeos que se realicen.

    /* responsive styles */
    @media only screen and (max-width: 600px) {
        <!-- Styles Here -->
    }

##### Otros Estilos

Los estilos vistos hasta ahora son de gran ayuda a la hora de maquetar emails responsive, a parte de estos puedes ver en la siguiente lista algunas clases que nos son de gran ayuda como tamaños en la tipografía, poner en bloque un elemento, esconder elementos en desktop y mostrar en movile, entre otros.


###### Componentes de bloque:

Ocultar un elemento 

    .hide {
        display: none !important;
        display: none;
    }

Poner en bloque un elemento 

    .blockwrap {
        display: block !important;
    }

Mostrar un elemento 

    .showme {
        display: block !important;
        width: auto !important;
        overflow: visible !important;
        float: none !important;
        max-height: inherit !important;
        max-width: inherit !important;
        line-height: auto !important;
        margin-top: 0px !important;
        visibility: inherit !important;
    }

Mover un elemento hacia abajo 

    *[class].movedown {
        display: table-footer-group !important;
    }

Mover un elemento hacia arriba

    *[class].moveup {
        display: table-header-group !important;
    }

###### Estilos para tipografía

Alinear a la derecha

    *[class].textright {
        text-align: right !important;
    }

Alinear a la izquierda    

    *[class].textleft {
        text-align: left !important;
    }

Alinear al centro    

    *[class].textcenter {
        text-align: center !important;
    }
Dar un tamaño de fuente _ej: 27px_

    *[class].font27 {
        font-size: 27px !important;
        font-weight: normal !important;
        line-height: 27px !important;
    }
###### Anchos y Altos de un elemento

Altura de un elemento _ej: 10px_

    *[class].h10 {
        height: 10px !important;
    }

Anchura de un elemento _ej: 320px_  

    *[class].w320 {
        width: 320px !important;
    }

## Estructura del contenido

A continuación se presenta una estructura básica para comenzar a desarrollar un email desde cero.

    <body style="margin:0; padding:0;" topmargin="0" leftmargin="0" marginheight="0" marginwidth="0">

        <!-- Línea Condicional para Outlook que previene el aumento de los spacers -->
        <!--[if gte mso 15]>
            <style type="text/css" media="all">
                tr { font-size:1px; mso-line-height-alt:0; mso-margin-top-alt:1px; }
            </style>
        <![endif]-->

        <table width="100%" border="0" cellspacing="0" cellpadding="0" bcolor="#fff">
            <tr>
                <td align="center" valign="top">
                    <!-- Empieza el Contenido -->
                        
                    <!-- Final de Contenido-->
                </td>
            </tr>
        </table>

    </body>


## Imágenes de Fondo y VML para Outlook 

Para poder usar imágenes en el background se usa un condicional para que el motor de Outlook después de la versión 2009 pueda renderizarlo, se usa `gte` para decir que es después de esa versión y el `9` para inlcluir la versión.

Linea Condicional para Outlook +9
     
     <!--[if gte mso 9]>
        <v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" style="width:600px; height:332px;">
        <v:fill type="tile" src="img/sydney.jpg" color="#000" />
        <v:textbox inset="0,0,0,0">
    <![endif]-->

            <!--[if gte mso 9]>
         </v:textbox>
     </v:rect>
     <![endif]-->


## Imágenes de alta resolución 

Diseñar la imagen de un porcentaje en pixeles mayor a como va ir en el `HTML`  con un ajuste de propiedades que hacen que la imagen sea más pequeña.

Ejemplo:

     <table width="100%" border="0" cellspacing="0" cellpadding="0" bcolor="#fff">
        <tr>
            <td align="center" valign="top">
                <!-- Empieza el Contenido -->
                    <table width="600">
                        <tr>
                            <td><img src="img/beach.png" alt="Beach" width="600" height="280"></td>
                        </tr>
                    </table>
                <!-- Final de Contenido-->
            </td>
        </tr>
    </table>




