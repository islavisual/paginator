Paginator
=========
Esta utilidad también está explicada en http://www.islavisual.com/articulos/desarrollo_web/paginator-clase-para-paginar-resultados-en-php

Clase para paginar resultados en PHP

Forma de uso
------------
Suponiendo que tenemos un array con los resultados a paginar, para crear el array de resultados a mostrar insertaríamos las siguientes líneas:

<pre>
  include "paginator.php";
  $paginator = new Paginator;
  $selectFiles = $paginator->SelectPage($_GET['npg'], $array_de_resultados);
</pre>
  
Estilos aplicados por CSS
-------------------------
Los estilos los podéis cambiar en la hoja de estilos CSS vuestra. Sólo tienen que estar definidos como los siguientes:

<pre>
   .paginator        { display: block; margin-top:20px; text-align: center; width: 100%; height:40px; clear:both }
   .paginator a      { background:#f0f0f0; color:#444; border:1px solid #e8e8e8; height:20px; width:20px; display:inline-block }
   #paginator_first  { background:url('images/action.first.png') no-repeat scroll 2px center #f0f0f0; }
   #paginator_before { background:url('images/action.before.png') no-repeat scroll 2px center #f0f0f0; }
   #paginator_next   { background:url('images/action.next.png') no-repeat scroll 2px center #f0f0f0; }
   #paginator_last   { background:url('images/action.last.png') no-repeat scroll 2px center #f0f0f0; }
</pre>

Y para insertar los controles de páginas anteriores y siguientes deberíamos escribir la siguiente línea:
<pre>
$paginator->ShowControls();
</pre>

Si, por ejemplo, estamos usando un blog y queremos que además filtre por categoría, deberíamos cambiar la instrucción anterior por la siguiente:

<pre>
   $category_param = "";
   if($_GET['cat'] != "") $category_param = "?cat=".$_GET['cat'];
   $paginator->ShowControls($_SERVER['PHP_SELF'].$category_param);
</pre>

<strong>cat</strong> es el parámetro pasado por URL indicador de la categoría y la clase, cuando detecte que viene por parámetros algo más que el nombre del PHP, añadira el parámetro de página, si es necesario.

Además, como véis, se puede mandar la URL por parámetro y si no se envía cogerá por defecto la URL actual.

