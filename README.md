## Cambios realizados

Durante el desarrollo del Ejercicio 1 se realizaron las siguientes mejoras y correcciones al servicio PHP:

---

###  Modularización del proyecto

Se creó una estructura de carpetas para organizar el código:


### Cambios clave realizados en el código

#### `api.php`

Se agregó la llamada correcta al método que devuelve los datos:

```php
require_once("modelo/valida.php");
$valida = new Valida();
echo $valida->ObtenerResponse();  // Línea agregada

valida.php
Se implementó el método ObtenerResponse() para devolver un JSON válido:

require_once("objeto.php");

class Valida {
    public function ObtenerResponse() {
        $obj1 = new Objeto("carro", "mediano", "rojo");
        $obj2 = new Objeto("moto", "pequeño", "negro");

        $respuesta = array("listaobjetos" => [$obj1, $obj2]);

        return json_encode($respuesta, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
    }
}


objeto.php
Se definió la clase Objeto con sus propiedades públicas:

class Objeto {
    public $tipo;
    public $tamanio;
    public $color;

    public function __construct($tipo, $tamanio, $color) {
        $this->tipo = $tipo;
        $this->tamanio = $tamanio;
        $this->color = $color;
    }
}

