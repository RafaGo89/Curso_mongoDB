# Comandos básicos de MongoDB

## Crear o seleccionar una base de datos en MongoDB. La nueva base de datos no se guardara hasta que se le añada una colección
```js
use  nombreBaseDeDatos
```

### Mostrar bases de datos existentes
```js
show  dbs
```

### Mostrar  características  de  una  base  de  datos  en  concreto

 ```js
 db.stats()
```

### Añadir una colección (tabla) a una base de datos
```js
db.createCollection("usuarios")
```
