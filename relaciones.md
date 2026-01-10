# Relaciones

## Al igual que en las bases de datos SQL, en MongoDB se pueden crear relaciones entre documentos para representar diferentes estructuras de datos

### Relación Uno a Uno incrustado (insertamos un documento dentro de otro documento)

```js
db.usuarios.insertOne({
  "nombre": "Sara",
  "email": "sara@ejemplo.com",
  "perfil": {
    "carrera": "administración",
    "edad": 30
  }
})
```

### Relación Uno a Uno referencias (insertamos un documento dentro de otro documento)

#### En la colección "departamentos" insertamos 2 documentos que representan nuestros departamentos
```js
db.departamentos.insertMany([
  {
    "_id": 101,
    "nombre": "Ventas"
  },
  {
    "_id": 102,
    "nombre": "Recursos humanos"
  }
])
```

#### En la colección "empleados" insertamos un empleado donde un campo sea el id del departamento al que pertenece

```js
db.empleados.insertOne({
  "nombre": "Juan",
  "correo": "juan@ejemplo.com",
  "edad": 35,
  "departamentoId": 101
})
```

#### Creamos una constante donde almacenamos la búsqueda de un empleado por su correo

```js
const empleado = db.empleados.findOne({"correo": "juan@ejemplo.com"})
```

####  Por medio de otra consulta, y empleando la consulta guardada en la constante, podemos obtener los datos del departamento al que pertenece ese empleado

```js
db.departamentos.findOne({"_id": empleado.departamentoId})
```
