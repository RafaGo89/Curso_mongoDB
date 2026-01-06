# Objecto cursor

## El objeto cursos es como una ventana que nos permite ver los documentos que se almacenan en una colección. Al ser un objeto, este cuenta con diferentes métodos.

## Método forEach(): permite iterar sobre los documentos y realizar operaciones con cada uno de ellos.

### Iteramos sobre todos los documentos de la colección "usuarios" e imprimimos solo el nombre

```js
db.usuarios.find().forEach(function(usuario){
  print(usuario.nombre)
})
```

## Método limit(): permite limitar o truncar la cantidad de documentos vistos en una consulta find

### Obtener los 3 primeros documentos de  la colección usuarios
```js
db.usuarios.find().limit(3)
```

## Método skip(): permite saltarse un número dado de registros y mostrar los restantes

###  Saltarse los primeros ocho documentos de la colección "usuarios" y mostrar el resto
```js
db.usuarios.find().skip(8)
```

### Saltarse los primeros 5 documentos de la colección "usuarios" y limitar la consulta a 3 resultados
```js
db.usuarios.find().skip(5).limit(3)
```

##  Método sort(): permite ordenar los documentos ascendentemente (1) o descendentemente (-1) por medio de un campo o atributo

### Ordenar los documentos de la colección "usuarios" por el campo edad, de menor a mayor
```js
db.usuarios.find().sort({edad: 1})
```

### Ordenar los documentos de la colección "usuarios" por el campo edad, de mayor a menor
```js
db.usuarios.find().sort({edad: -1})
```
