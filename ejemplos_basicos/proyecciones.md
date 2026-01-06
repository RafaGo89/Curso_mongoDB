# Proyecciones

## Es básicamente decidir que atributos de los documentos mostrar and hacer una consulta find. Se usa el uno (1) para indicar que atributos mostrar, o cero (0) para no incluirlos.

### Obtener id y nombre de la colección "usuarios"
```js
db.usuarios.find({}, {_id: 1, nombre: 1})
```

### Obtener el titulo y autor de los libros de la colección "biblioteca"
```js
db.biblioteca.find({}, {_id: 0, "libro.titulo": 1, "libro.autor": 1})
```

### Obtener todos los atributos de los libros de la colección "biblioteca", excepto el año de publicación
```js
db.biblioteca.find({}, {year: 0})
``` 
