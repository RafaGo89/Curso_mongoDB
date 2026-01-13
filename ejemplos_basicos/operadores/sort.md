# Sort

## Sort nos permite ordenar los resultados de las queries find

### Obtener los documentos donde la existencia sea mayor o igual a 10 y el precio sea menor o igual a 1000. Ordenar el resultado de mayor a menor de acuerdo a a la existencia

```js
db.productos.find({
  $expr: {
    $and: [
      {$gte: ["$existencia", 10]},
      {$lte: ["$precio", 1000]}
    ]
  }
}).sort({existencia: -1})
```

### Obtener los documentos donde la existencia sea mayor o igual a 10 y el precio sea menor o igual a 1000. Ordenar el resultado de menor a mayor de acuerdo a a la existencia

```js
db.productos.find({
  $expr: {
    $and: [
      {$gte: ["$existencia", 10]},
      {$lte: ["$precio", 1000]}
    ]
  }
}).sort({existencia: 1})
```

### Obtener los documentos donde la existencia sea mayor o igual a 10 y el precio sea menor o igual a 1000. Ordenar el resultado de menor a mayor de acuerdo a a la existencia, y también de menor a mayor de acuerdo al precio

```js
db.productos.find({
  $expr: {
    $and: [
      {$gte: ["$existencia", 10]},
      {$lte: ["$precio", 1000]}
    ]
  }
}).sort({existencia: 1, precio: 1})
```
