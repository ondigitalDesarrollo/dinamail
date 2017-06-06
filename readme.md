# Documentación para crear emails dinámicos

## Historia del Correo Electrónico

El desarrollo de emails no ha cambiado en los últimos 25 años, su estructura esta compuesta de html y CSS inline.

Los emails no trabajan como una página web y visceversa, el auge de los dispositivos móviles a cambiado las técnicas de desarrollo para diferentes proveedores de correo electrónico, entre las más usadas según la compañia Litmus (Compañia de Massachusetts dedicada a la creación de software para desarrollar emails efectivos y en colaboración con equipos de trabajo) se encuentran:

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

A continuación una lista de los elementos más usados para el desarrollo de emails, la propiedad `colspan="2"` que une dos columnas debería no usarse debido a que el cliente Outlook no tiene el soporte.

    <table>
        <tr>
            <td></td>
        </tr>
    </table>

    <span>Título</span>

    <div></div>

    <img src="" alt="">


## Buenas Prácticas en Plantillas de Estilos para email.





