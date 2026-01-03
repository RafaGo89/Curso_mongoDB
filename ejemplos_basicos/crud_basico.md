# CRUD básico en MongoBD

## Insertar dos nuevos documentos (filas) en una colección
```js
db.usuarios.insertOne({
	nombre: "Rafael",
	edad: 22,
	ciudad: "Guadalajara"
})
```
```js
db.usuarios.insertOne({
	nombre: "Thiare",
	edad: 23,
	ciudad: "San Jose"
})
```

### Leer todos los documentos de una colección
```js
db.usuarios.find()
```

### Actualizar un campo de un solo documento, actualiza el primero que se encuentre
```js
db.usuarios.updateOne(
	{nombre: "Rafael"},
	{$set: {edad: 25}}
)
```

### Eliminar un documento empleando un campo como filtro, elimina el primero que encuentra

```js
db.usuarios.deleteOne({edad: 25})
```

## Creación de una colección nueva

### Inserción de nuevos documentos en la colección recién creada
```js
db.tareas.insertOne({
	usuarioId: ObjectId("69547f559fda59cf0bc63f8e"),
	descripcion: "Preparar informe mensual",
	estado: "Pendiente"
})
```
```js
db.tareas.insertOne({
	usuarioId: ObjectId("69547f559fda59cf0bc63f8e"),
	descripcion: "Preparar carta",
	estado: "Pendiente"
})
```
```js
db.tareas.insertOne({
	usuarioId: ObjectId("6957275f761354439ecd7cdb"),
	descripcion: "Asistir a la reunión de medio día",
	estado: "Pendiente"
})
```

### Lectura de las tareas asignadas a un usuario en concreto usando su id
```js
db.tareas.find({usuarioId: ObjectId("69547f559fda59cf0bc63f8e")})
```
### Actualización del estado de una tarea, usando el id de la tarea como criterio de búsqueda
```js
db.tareas.updateOne(
	{_id: ObjectId("695726d5761354439ecd7cda")},
	{$set: {estado: "Completada"}}
)
```

### Actualización de una tarea agregando un nuevo campo, usando el id de la tarea como criterio de búsqueda
```js
db.tareas.updateOne(
	{_id: ObjectId("69572666761354439ecd7cd9")},
	{$set: {observacion: "Esta tarea no corresponde al usuario"}}
)
```

### Borrado de una tarea usando el id como criterio de búsqueda
```js
db.tareas.deleteOne({_id: ObjectId("69572666761354439ecd7cd9")})
```
