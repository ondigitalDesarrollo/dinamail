# Documentación Para Crear Emails Dinámicos.

## Historia del Correo Electrónico.

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

## Entornos de Trabajo. 

Para estructurar rápidamente tablas se recomienda usar el plugin de  [emmet](https://emmet.io/) e instalarlo en tu editor de código favorito.

### Ejemplos:

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

## Bases de Desarrollo Para Email.

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

### DOCTYPE.

Se recomienda el siguiente doctype porque hay algunos clientes de correo que necesitan de esta propiedad para poder mostrar el email.

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml">

### Metatag Viewport.
Meta etiqueta para que el browser interprete el tamaño del dispositivo y permita el uso de mediaqueries.

    <!-- view port meta tag -->
    <meta name="viewport" content="width=device-width, initial-scale=1">

### Hacks CSS head.

##### Evitar que iPhone nos agrande las fuentes.

    * {
        -webkit-text-size-adjust: none;
        -ms-text-size-adjust: none;
        max-height: 1000000px;
    }

##### Quitar el padding del Cliente Outlook para PC (2013) en los elementos `<a></a>`.

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

##### Media Queries.

En el caso de las media queries se intenta cubrir la gran cantidad de dispositivos de acuerdo a los Clientes de Email en que se valla a usar el correo, en este caso se usa un breakpoint de **600px** para abaracar gran cantidad de dispositvos, esta medida _puede variar_  e incluso se pueden insertar más breakpoints dependiendo los resultados que querramos obtener, según los testeos que se realicen.

    /* responsive styles */
    @media only screen and (max-width: 600px) {
        <!-- Styles Here -->
    }

##### Otros Estilos.

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

###### Estilos para tipografía.

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
###### Anchos y Altos de un elemento.

Altura de un elemento _ej: 10px_

    *[class].h10 {
        height: 10px !important;
    }

Anchura de un elemento _ej: 320px_  

    *[class].w320 {
        width: 320px !important;
    }

## Estructura del contenido.

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


## Imágenes de Fondo y VML para Outlook.

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


## Imágenes de alta resolución.

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

## Organizar el CSS para EMAIL.

En email los archivos no se usan archivos externos, los estilos se usan en línea y se intenta comprimir el archivo para que cargue más rápido.

Para evitar que los clientes de correo nos anulen las clases se usa `!important` en la propiedad de la clase para que pueda servir y visualizarse correctamente, con esto evitamos que nuestro email se estropee.

Ejemplo

    <!-- Clases CSS después del HEAD para la construcción del email -->
    <style type="text/css">
        /* hacks */
        * {
            -webkit-text-size-adjust: none;
            -ms-text-size-adjust: none;
            max-height: 1000000px;
        }
        table {
            border-collapse: collapse !important;
        }
        #outlook a {
            padding: 0;
        }
        .ReadMsgBody {
            width: 100%;
        }
        .ExternalClass {
            width: 100%;
        }
        .ExternalClass * {
            line-height: 100%;
        }
        .ios_geo a {
            color: #1c1c1c !important;
            text-decoration: none !important;
        }

        .headline{
            font-family: serif;
            color: #1c1c1c;
            font-size: 30px;
        }
        /* responsive styles */
        @media only screen and (max-width: 600px) {
            /* global styles */
            .hide {
                display: none !important;
                display: none;
            }
            .blockwrap {
                display: block !important;
            }
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
            *[class].movedown {
                display: table-footer-group !important;
            }
            *[class].moveup {
                display: table-header-group !important;
            }
            /* font styles */
            *[class].textright {
                text-align: right !important;
            }
            *[class].textleft {
                text-align: left !important;
            }
            *[class].textcenter {
                text-align: center !important;
            }
            *[class].font27 {
                font-size: 27px !important;
                font-weight: normal !important;
                line-height: 27px !important;
            }
            /* Color Fuente */
            *[class].fontRed{color: #ff0000 !important;}

            /* width and heights */
            *[class].h10 {
                height: 10px !important;
            }
            *[class].w320 {
                width: 320px !important;
            }

             /* Colores de Fondo */
            *[class].bgGray{ background-color: #c1c1c1 !important}
        }

    </style>


    <!-- Estructura del Email  -->

    <table width="100%" border="0" cellspacing="0" cellpadding="0"  bgcolor="#cccccc">
        <tr>
            <td align="center" valign="top" align="center">
                <!-- Empieza el Contenido -->
                    <table width="600" bgcolor="000000" align="center" class="bgGray">
                        <tr>
                            <td align="center" height="300">
                                <span class="fontRed" style="font-family: arial; font-size: 20px; color: #ffffff;">
                                  Este es mi Título  
                                </span>
                            </td>
                        </tr>
                    </table>
                <!-- Final de Contenido-->
            </td>
        </tr>

# Técnicas de Maquetación y Diseño para Emails.

Para cambiar elementos relacionados al diseño, tamaños o estructura hay que tener en cuenta el dispositivo en que se visualiza el email, en un elemento en móvil se vería vertical y en escritorio los elementos se verían horizontales.

## Técnica de Stacking

Es la posición de elementos en forma vertical. Es una técnica para un “apilamiento de enfoque” y también afecta el orden. 

Ejemplo:

Hay dos tablas, como contenedores, a ambas se aplica la clase “blockwrap”. Si se desea cambiar el orden, hay una clase declarada en Styles: “movedown” y “moveup” respectivamente. Esas clases deben incluirse en “inline style” junto a “blockwrap”. El resultado sería el cambio de la posición, es decir, el “Module right” aparecerá sobre el “Module left”.

Estilos CSS:

    /* Clases CSS usadas para la técnica de stacking */

    /* Mover Elementos arriba o abajo */
    *[class].movedown {
        display: table-footer-group !important;
    }
    *[class].moveup {
        display: table-header-group !important;
    }

    /* Poner los elementos en bloque  */
    .blockwrap {
        display: block !important;
    }

    /* Tamaños de acuerdo a la resolución */
    *[class].w320 {
        width: 320px !important;
    }



Código HTML:

    <!--Comienzo Contenido-->
    <table width="600" align="center" bgcolor="#cccccc" class="w320">
        <tr>
            <td width="300" align="center" class="w320 blockWrap moveDown">
                
                <table>
                    <tr>
                        <td>
                            <span style="font-family:arial;color:#ff0000;font-size:20px;">
                                Module Left
                            </span>
                        </td>
                    </tr>
                </table>

            </td>
            <td width="300" align="center" class="w320 blockWrap moveUp">

                <table>
                    <tr>
                        <td>
                            <span style="font-family:arial;color:#ff0000;font-size:20px;">
                                Module Right
                            </span>
                        </td>
                    </tr>
                </table>

            </td>
        </tr>
    </table>
     <!--Final Contenido-->

La técnica de Stacking proporcionan mayor libertad y control en el diseño.

## Técnica de Spacers

Los spacers son imágenes de **_1px x 1px_** para controlar el espacio en los emails, consiste en colocar este tipo de imágenes para conservar la maquetación debido a que algunos motores son demasiado antiguos y el mail se pueda ver cortado.

La técnica consiste en colocar un elemento _.gif_ en los lugares en que necesitemos un espacio, margen, padding, etc. Para ello se inserta dentro de una etiqueta **img** así: `<img src="img/spacer.gif" width="10" class="w50 h50">`

# Buenas Prácticas para Tener en Cuenta.

Estas son unas recomendaciones más útiles para mitigar los problemas más comunes en el desarrollo de HTML para emails.

## Imágenes.

Es importante entender que la propiedad de CSS “display:block” puede ayudarnos a evitar problema de espacios no necesarios en **Outlook**.

Esta propiedad puede ser usada a gusto, pero es mejor siempre incluirla. Lo mismos aplica para la propiedad `“border=”0”`.

Ejemplo:

    <img src="img/beach.png" width="600" height="280" style=”display:block” border=”0”>

## Tablas.

Tablas son la unidad básica de construcción de nuestros emails. Debemos incluir estas propiedades para asegurarnos que van a ser interpretadas en su forma mas pura. También es mejor siempre declarar un valor para **“aling”** y **“valign”**.

Ejemplo: 

    <table width="100%" border="0" cellspacing="0" cellpadding="0">
        <tr>
             <td align="center" valign="top"> </td>
        </tr>
    </table>


## El <BODY> tag.

Para evitar que los servicios de email de web añadan estilos innecesarios a nuestro documento, debemos declarar estas propiedades en el `<body>`.

## Colores de texto y de fondo.

Siempre usa los 6 dígitos cuando necesites declarar un color en el CSS en línea y solo en formato hexadecimal.

Ejemplo:

    <td style=”color:#000000 font-size: 14px, background-color:#ffffff”>texto va aquí</td>

## Texto y Fuentes.

Para declarar nuestras fuentes, es mejor siempre incluir todos los aspectos de tu fuente como propiedades CSS en línea. Nunca uses el elemento `<font>` o el elemento `<p>`.Estas declaraciones deben ir en el elemento inmediato del texto

Ejemplo:

    <td style="font-family:Arial, Helvetica, sans-serif; font-size: 17px; line-height:22px; color:#FFFFFF;">text va aqui</td>

## Links.

Los programas de email tienden a resaltar links en el texto. Para prevenir eso, siempre debemos declarar en el estilo en línea, el color y el tipo de decoración de texto que necesitamos.

Ejemplo:

    <a href=”” style="text-decoration:none; color:#ffffff; text-decoration:underline”>link va aqui</a> 

## Mobile Links.

En dispositivos mobiles, texto que parezca una dirección, un teléfono o una fecha, va a ser resaltado como un link automáticamente. La solución es una mezcla de CSS y de HTML.

Ejemplo:

    <td style="font-family:Arial, Helvetica, sans-serif; font-size: 17px; line-height:22px; color:#FFFFFF;">
        Estaremos en diciembre 28, 2016.
    </td>

Solución:

    <style>
        .ios_text a { color:#000000 !important; text-decoration:none !important; }
    </style>

    <td style="font-family:Arial, Helvetica, sans-serif; font-size: 17px; line-height:22px; color:#000000;">
        Estaremos en <span class=”ios_fecha”>diciembre 28, 2016.</span>
    </td>

## Espacios entre Tablas.

Es recomendable usar una tabla con una imagen transparente (spacers) para tener más control de los espacios entre tablas.

    <table width="100%" border="0" cellspacing="0" cellpadding="0">
    <tr>
        <td align="center" valign="top">
            <img src="img/spacer.gif" width="50" class="w10">
        </td>
    </tr>
    </table>


## Outlook 2013

Para evitar el desbordamiento de los spacer en Outlook 2013 se recomienda añadir la propiedad de css `line-height` igual a la de el tamaño y la altura de la imagen o el bloque.

     <!-- borde de arriba -->
    <table width="640" border="0" cellpadding="0" cellspacing="0" class="w380" cellmargin="0">
        <tr>
            <td width="10" style="line-height:10;"><img src="img/PROJEKTO-welcome-DESK_12.png" style="display:block"></td>
            <td width="620" bgcolor="#ffffff" class="w360" style="line-height:10;"></td>
            <td width="10" style="line-height:10;"><img src="img/PROJEKTO-welcome-DESK_14.png" style="display:block"></td>
        </tr>
    </table>
    <!-- /borde de arriba -->

# Usar WebFonts en Email

Usar webfonts en Email igual que a como en la web es un poco más complicado, los únicos clientes que lo permiten son Android Mail y Apple Mail, por ello debemos asegurarnos de tener fallbacks y hacks en caso de que la fuente no se renderize correctamente, cambiandola por otra opción o tener una tipografía por defecto.

Para añadir una Webfont se inserta el link y luego se llama desde el CSS en línea

Ejemplo

    <!-- HTML Code -->
    <link href="https://fonts.googleapis.com/css?family=Bungee+Shade" rel="stylesheet">

    /* CSS Code */
    <span style="font-family: 'Bungee Shade', cursive;" > Hello I´m WebFont </span>

# Usar HTML5 Video

Para 


















