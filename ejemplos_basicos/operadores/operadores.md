# Operadores

## Los operadores son palabras claves que nos permiten realizar comparaciones, filtros y evaluaciones en consultas find en MongoDB

### Operadores de comparación

 - $eq: igual (=).
 - $ne: no igual (!=).
 - $gt: mayor que (>).
 - $lt: menor que (<).
 - $gte: mayor o igual que (>=).
 - $lte: menor o igual que (<=).

### Operadores lógicos

 - $and
 - $or
 - $not
 - $nor: (evalúa expresiones y devuelve los documentos que no cumplan ninguna de ellas)

### Operadores de elemento (son utilizados para evaluar la existencia de campos en documentos)

 - $exists: comprueba si un campo existe.
 - $type: filtra por tipo de dato.

### Operados de evaluación

 - $regex: permite usar expresiones regulares para buscar patrones de cadenas.
 - $expr: realiza evaluaciones de expresiones.
 - $jsonSchema: valida documentos según un esquema JSON.

### Operados de arreglo

 - $all: se utiliza para encontrar documentos con un arreglo que contiene todos los elementos especificados.
 - $elemMatch: encuentra documentos donde al menos un elementos satisface una condición.
 - $size: compara el tamaño de un arreglo con un valor específico.

