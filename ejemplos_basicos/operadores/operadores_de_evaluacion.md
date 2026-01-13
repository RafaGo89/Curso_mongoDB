#  Operadores de evaluación

## Nos permiten evaluar condiciones más complejas o de una manera distinta

### Buscar los documentos donde el nombre inicie con la letra "T"

```js
db.productos.find({nombre: {$regex: /^T/}})
```

### Buscar los documentos donde el nombre inicie por la palabra "iPhone" (sensible a mayúsculas)

```js
db.productos.find({nombre: {$regex: /^iPhone/}})
```

### Esto es una búsqueda diferente a la anterior

```js
db.productos.find({nombre: {$regex: /^IPHONE/}})
```

### Con $expr podemos combinar distintas evaluaciones, aquí realizamos una búsqueda de los documentos donde la existencia sea mayor a 10 y el precio menor a 700

```js
db.productos.find({
  $expr: {
    $and: [
      {$gt: ["$existencia", 10]},
      {$lt: ["$precio", 700]}
    ]
  }
})
```

