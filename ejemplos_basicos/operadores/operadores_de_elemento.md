# Operadores de elemento

## Nos permiten realizar búsquedas de acuerdo a la existencia o tipo de una atributo en un documento

### Obtener los documentos que contengan un campo llamado "consumible"

```js
db.productos.find(
  {
    consumible: {$exists: true}
  }
)
```

### Obtener los documentos que contengan un campo llamado "fechaVencimiento"

```js
db.productos.find(
  {
    fechaVencimiento: {$exists: true}
  }
)
```

### Obtener los documentos que NO contengan un campo llamado "consumible"

```js
db.productos.find(
  {
    consumible: {$exists: false}
  }
)
```

### Obtener todos los documentos que tengan un campo llamado "consumible" que sea de tipo "bool"

```js
db.productos.find(
  {
    consumible: {$type: "bool"}
  }
)
```
