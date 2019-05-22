# Msg-Lite for Laravel.

Versión minimalista de mensaje para mostrar mensajes al usuario, la cual hace uso de sweetalert2 y mensajes desde el back.

## Requisitos

Debido a que hace uso del paquete js de sweetalert2, el mismo es requerido para el funcionamiento del script, por lo que se puede seguir las indicaciones de la [pagina oficial](https://sweetalert2.github.io/#usage) o simplemente utilizar esto tal cual, debido a que se realiza la inclusión del paquete(CDN) desde el mismo.

## Utilización:

Para mostrar el mensaje se espera que desde el back la vista que retorne incluya dos mensajes con nombre: 

- message : EL cual contendrá el mensaje a mostrar.
- message_type : EL cual se encarga de la parte visual (color de tema utilizado en el mensaje de sweetaler2) y acepta por valores.
    - error
    - info
    - question
    - success
    - warning

### Ejemplos (Laravel)

_Simple_

```php
return route('route.name')->with('message', 'Welcome')->with('message_type', 'success');
```

_Con redirect y utilizando traducción._

```php
return redirect()->route('route.name')->with('message', trans("msg.created", ['model' => trans('theme.theme')]))->with('message_type', 'success');
```

## Notas

A pesar de estar desarrollado principalmente para **Laravel** con solo cambiar la sintaxis de blade por la de otro motor de plantilla o incluso por php puro se puede utilizar sin ningún problema.