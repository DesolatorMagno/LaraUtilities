# Trait for Msg-Lite.

Trait especifico para MSg-Lite para volver mas sencillo el proceso de la creación de mensajes.


## Utilización:

- Incluir el **message.blade** (msg-lite) en el tema o vista especifica (en el readme de msg-lite se explica como funciona el front)
- Copiar y pegar el archivo a **App/Traits** y luego usarlo dentro del controlador que se quiera (luego mejorare esta parte).
- Para crear el mensaje en session llamar a una de las funciones y pasar por parametro el mensaje, de esta manera.
- Retornar la vista que se desea luego del paso anterior.

```php
$this->success('Mensaje de Exito!');
return route('route.name')
```

### msg-lite sin trait vs con trait

_Simple_
```php
return route('route.name')->with('message', 'Welcome')->with('message_type', 'success');
```

_Con trait_
```php
$this->success('Welcome');
return route('route.name');
```

## Notas

- Aun faltas pruebas mas rigurosas.
- La versión light solo funciona con 1 mensaje a la vez y no se pueden hacer mayores modificaciones al diseño del mensaje, esto esta pendiente para la próxima versión que sera mas completa.