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

### Relación Uno a Muchos incrustada (insertamos en un documento una lista de documentos)

#### En una entrada a un blog se pueden realizar muchos comentarios

```js
db.blog.insertOne({
  "_id": 1,
  "titulo": "Entrada número 1",
  "contenido": "buen día",
  "comentarios": [
    {
      "usuario": "Rosita",
      "texto": "Hola, buen día"
    },
    {
      "usuario": "José",
      "texto": "¿Cómo te va?"
    }
  ]
})
```

### Relación Muchos a Muchos incrustado (insertamos en un documento una lista de documentos, que a su vez contiene referencia 'hacia fuera')

#### En la colección "editores" insertamos un nuevo editor y una lista de las publicaciones a las que tiene derecho de editar. En la lista de publicaciones también hay un atributo que especifica la lista de los editores de esa publicación
```js
db.editores.insertOne({
  _id: 1,
  nombre: 'Pedro Juarez',
  publicaciones: [
    {
      "_id": 1,
    "titulo": "Buen día",
    "contenido": "¿Como despertaron?",
    "editoresRelacionados": [1, 2]
    },
    {
      "_id": 2,
    "titulo": "Ayuda",
    "contenido": "¿Alguien que me ayude con algo?",
    "editoresRelacionados": [1]
    }
  ]
})
```

### Relación Uno a Muchos referencia (en un documento se inserta una lista de id's que referencian a otro documento)

#### Insertamos en la colección "inventario" un producto, uno de sus atributos es "reseñas" que es una lista de id's que referencia a otra colección

```js
db.inventario.insertOne({
  "_id": 1,
  "nombre": "TV",
  "precio": 3200,
  "reseñas": [1, 2]
})
```

#### En la colección "reseñas" insertamos 2 documentos de reseñas de 2 usuarios distintos. Estas son las reseñas a las que se hacía referencia en la colección "inventario"

```js
db.resenas.insertMany([
  {
    "_id": 1,
    "usuario": "Jorge",
    "comentario": "Buen producto"
  },
  {
    "_id": 2,
    "usuario": "Ivette",
    "comentario": "No es la gran cosa"
  }
])
```

### Relación Muchos a Muchos referencia (en un documento se inserta una lista de id's que referencian a otro documento. A su vez, en el otro documento también se encuentra una lista de id's que referencian al primer documento)

#### En la colección "cursos" insertamos un documento que representa un cursos de programación con atributo de los estudiantes que están tomándolo

```js
db.cursos.insertOne({
  "_id": 1,
  "nombre": "Curso de programación",
  "descripción": "Aprende a programar en JavaScript",
  "estudiantes": [1, 2]
})
```

#### En la colección "estudiantes" insertamos los diferentes estudiantes que toman cursos, donde por medio de una lista se representan los diferentes cursos a los que asisten

```js
db.estudiantes.insertMany([
  {
    "_id": 1,
    "nombre": "Pedro",
    "cursos": [1, 3]
  },
  {
    "_id": 2,
    "nombre": "Maria",
    "cursos": [1, 2]
  }
])
```
