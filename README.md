Paginator
=========

Clase para paginar resultados en PHP

Forma de uso
============
  <code>include "paginator.php";</code>
  <code>$paginator = new Paginator;</code>
  
Estilos aplicados por CSS
-------------------------

<p>Los estilos los podéis cambiar en la hoja de estilos CSS vuestra. Sólo tienen que estar definidos como los siguientes:</p>
                                <pre class="prettyprint">
<code>
.paginator { display: block; margin-top:20px; text-align: center; width: 100%; height:40px; clear:both }
.paginator a { background:#f0f0f0; color:#444; border:1px solid #e8e8e8; height:20px; width:20px; display:inline-block }
#paginator_first   { background:url('../images/action.first.png') no-repeat scroll 2px center #f0f0f0; }
#paginator_before	{ background:url('../images/action.before.png') no-repeat scroll 2px center #f0f0f0; }
#paginator_next 	{ background:url('../images/action.next.png') no-repeat scroll 2px center #f0f0f0; }
#paginator_last 	{ background:url('../images/action.last.png') no-repeat scroll 2px center #f0f0f0; }
</code></pre><br>

								<p>Las imágenes las podéis descargar pinchando <a href="paginator_images.zip">aquí</a>.</p>

                                
                                <h2>Forma de usarla</h2>
                                <p>Suponiendo que tenemos un array con los resultados a paginar, para crear el array de resultados a mostrar insertaríamos las siguientes 2 líneas:</p>
                                <pre class="prettyprint">
<code>
$paginator = new Paginator;
$selectFiles = $paginator->SelectPage($_GET['npg'], $array_de_resultados);
</code></pre><br>

                                <p>Y para insertar los controles de páginas anteriores y siguientes deberíamos escribir la siguiente línea:</p>
                                <pre class="prettyprint">
<code>
$paginator->ShowControls();
</code></pre><br>

								<p>Si, por ejemplo, estamos usando un blog y queremos que además filtre por categoría, deberíamos cambiar la instrucción anterior por la siguiente:</p>
                                <pre class="prettyprint">
<code>
$category_param = "";
if($_GET['cat'] != "") $category_param = "?cat=".$_GET['cat'];
$paginator->ShowControls($_SERVER['PHP_SELF'].$category_param);
</code></pre><br>
								
                                <p>cat es el parámetro pasado por URL indicador de la categoría y la clase, cuando detecte que viene por parámetros algo más que el nombre del PHP, añadira el parámetro de página, si es necesario.</p>
                                <p>Además, como véis, se puede mandar la URL por parámetro y si no se envía cogerá por defecto la URL actual.</p>
