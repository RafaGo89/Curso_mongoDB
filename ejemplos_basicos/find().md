# Comando find()

## Usado para realizar operaciones de lecturas

### Lectura de todos los documentos
```js
db.usuarios.find()
```

### Lectura de los documentos donde el correo sea juan@example.com (búsqueda exacta)
```js
db.usuarios.find({correo: "juan@example.com"})
```

### Lectura de los documentos donde la edad sea mayor a 30 años (>)
```js
db.usuarios.find({edad: {$gt: 30}})
```

### Lectura de los documentos donde la edad sea mayor o igual 30 años (>)
```js
db.usuarios.find({edad: {$gte: 30}})
```

### Lectura de los documentos donde la edad sea menor a 30 años (<)
```js
db.usuarios.find({edad: {$lt: 30}})
```

### Lectura de los documentos donde la edad sea menor o igual 30 años (<)
```js
db.usuarios.find({edad: {$lte: 30}})
```

### Lectura de los documentos donde la edad esté en un rango de entre 25 y 35 años
```js
db.usuarios.find({edad: {$gte: 25, $lte: 35}})
```
