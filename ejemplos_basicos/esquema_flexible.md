# Esquema flexible

## En MongoDB la estructura de las colecciones puede ser flexible, es decir, los documentos pueden tener diferentes campos o atributos. Para hacer esto solo se debe crear la colección e insertar documentos

### Inserción de documentos con diferente estructura en la  misma colección "mi_colección"

```js
db.mi_coleccion.insertOne({
  nombre: "Ejemplo 1",
  edad: 25,
  intereses: ["MongoDB", "NoSQL"]
})
```

```js
db.mi_coleccion.insertOne({
  nombre: "Ejemplo 2",
  direccion: "123 Calle Principal",
  ciudad: "Ciudad Ejemplo"
})
```
