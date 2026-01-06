# Comandos updateOne(), updateMany() y replaceOne()

## updateOne(): actualiza el primer documento que encuentre donde el filtro aplicado se cumpla.

### Actualizamos la edad a 36 años, en el documento donde el nombre sea "Juan Pérez"
```js
db.usuarios.updateOne(
  {nombre: "Juan Pérez"},
  {$set: {edad: 36}}
)
```

## updateMany(): actualiza todos los documentos que cumplan con el filtro aplicado

### Modificar la edad de los usuarios a 35, donde la edad sea 40
```js
db.usuarios.updateMany(
  {edad: 40},
  {$set: {edad: 35}}
)
```

## replaceOne(): reemplaza (no actualiza) por completo el primer documento que cumpla filtro dado

### Reemplazamos el documento donde el nombre sea "María Gonzáles" por un nuevo documento
```js
db.usuarios.replaceOne(
  {nombre: "María González"},
  {nombre: "María Gómez", edad: 40, sexo: "Femenino"}
)
```

