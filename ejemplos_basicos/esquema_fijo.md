# Esquema fijo

## En MongoDB también es posible definir un esquema o estructura que tendrán los documentos en nuestras colecciones. Podemos definir campos, tipos de datos y restricciones.

### Creación de un nueva colección "empleados" donde se define una estructura a los documentos con 3 campos: nombre, correo y edad

```js
db.createCollection("empleados",{
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["nombre", "correo", "edad"],
      properties: {
        nombre: {
          bsonType: "string"
        },
        correo: {
          bsonType: "string"
        },
        edad: {
          bsonType: "int",
          minimum: 18
        }
      }
    }
  }
})
```

### Insertamos un nuevo documento exitosamente

```js
db.empleados.insertOne({
  nombre: "Rafael",
  correo: "rafa@ejemplo.com",
  edad: 22
})
```

### Esta inserción arrojará un error ya que no se está incluyendo el campo edad, y al inicio se definió que ese campo es obligatorio

```js
db.empleados.insertOne({
  nombre: "Juana",
  correo: "juana@ejemplo.com"
})
```

### Esta inserción también dará un error porque la edad es menor a 18, como en un principio se definió

```js
db.empleados.insertOne({
  nombre: "Pedro",
  correo: "pedro@ejemplo.com",
  edad: 15
})
```
