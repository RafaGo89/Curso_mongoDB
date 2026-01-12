# Operadores lógicos

## Permiten realizas filtros o evaluaciones

### Obtener todos los documentos donde el precio sea igual a 900

```js
db.productos.find({precio: {$eq: 900}})
```

### Obtener todos los documentos donde el precio sea mayor a 500

```js
db.productos.find({precio: {$gt: 500}})
```

### Obtener todos los documentos donde el precio sea menor a 500

```js
db.productos.find({precio: {$lt: 500}})
```

### Obtener todos los documentos donde la existencia sea mayor o igual a 10

```js
db.productos.find({existencia: {$gte: 10}})
```

### Obtener todos los documentos donde la existencia sea menor o igual a 10

```js
db.productos.find({existencia: {$lte: 10}})
```

###  Obtener todos los documentos donde el precio NO sea igual a 900

```js
db.productos.find({precio: {$ne: 900}})
```
