# Comando insertMany()

## Sirve para insertar varios documentos en una colección usando solo un comando.

### Primeramente creamos  una nueva colección
```js
db.createCollection("productos")
```

### Insertamos varios documentos en esa colección usando insertMany()
```js
db.productos.insertMany([
  {nombre: "Arroz", precio: 2000},
  {nombre: "Azúcar", precio: 3000},
  {nombre: "Frijol", precio: 6000}
])
```

### insertMany() y uso de id's personalizados
```js
db.productos.insertMany([
  {_id: 1, nombre: "Leche", precio: 5000},
  {_id: 2, nombre: "Café", precio: 3500}
])
```

