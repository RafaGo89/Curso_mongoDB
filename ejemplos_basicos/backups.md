# Backups y reseteos de bases de datos

## Crear respaldos en una base de datos en MongoDB

### Crear respaldo
```js
mongodump --db nombre_base_datos --out ruta_a_exportar
```
### Ejemplo
```js
mongodump --db nueva_db --out .
```

### Cargar el respaldo
```js
mongorestore --db nombre_base_datos ruta_de_donde_importar
```

### Ejemplo
```js
mongorestore --db nueva_db_copy nueva_db
```

##  Eliminar colecciones y bases de datos

### Eliminar una colección
```js
db.tareas.drop()
```

### Eliminar una base de datos (es necesario estar usando (comando *use*) la base de datos a eliminar)
```js
db.dropDatabase()
```
