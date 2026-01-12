# Operadores de lógicos

## Estos operadores nos permiten combinar varios operadores de comparación para realizar evaluaciones más complejas

### Encontrar los documentos donde el precio sea mayor a 500 y la existencia mayor o igual a 10

```js
db.productos.find({
  $and: [
    {precio: {$gt: 500}},
    {existencia: {$gte: 10}}
  ]
})
```

### Encontrar los documentos donde el precio sea menor a 400 ó que la existencia sea mayor o igual a 20

```js
db.productos.find({
  $or: [
    {precio: {$lt: 400}},
    {existencia: {$gte: 20}}
  ]
})
```

### Encontrar los documentos donde el precio NO sea mayor a 500 y la existencia mayor o igual a 10

```js
db.productos.find({
  $and: [
    {precio: {$not: {$gt: 500}}},
    {existencia: {$gte: 10}}
  ]
})
```

### Encontrar los documentos donde el nombre del producto sea "Laptop", el precio esté entre 400 y 800, y donde la existencia sea menor a 10

```js
db.productos.find({
  $and: [
	  {nombre: {$eq: "Laptop"}},
    {precio: {$gte: 400, $lte: 800}},
    {existencia: {$lt: 10}}
  ]
})
```
