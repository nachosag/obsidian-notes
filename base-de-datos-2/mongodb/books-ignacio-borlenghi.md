# Books

## Ejercicios

1. Importar el documento (utilizando todos los parámetros del mongoimport).

```javascript

```

2. Importar el documento especificando solamente el .Json (obtener conclusiones).

```javascript

```

3. Encontrar todos los libros de una categoría específica.

```javascript

```

4. Encontrar un libro por su isbn.

```javascript

```

5. Actualizar el número de páginas de un libro usando $set.

```javascript

```

6. Eliminar un campo de un documento usando $unset.

```javascript

```

5. Buscar todos los libros que no tienen el campo longDescription

```javascript

```

6. Añadir una nueva categoría a un libro existente usando $addToSet.

```javascript

```

7. Actualizar el estado de un libro usando $set.

```javascript

```

8. Buscar todos los libros publicados después del 2010.

```javascript

```

9. Buscar todos los libros con más de 500 páginas.

```javascript

```

10. Buscá libros con menos de 150 páginas.

```javascript

```

11. Buscá libros que tengan entre 100 y 200 páginas $and

```javascript

```

12. Eliminar un libro por su _id.

```javascript

```

13. Incrementar el número de páginas de un libro usando $inc.

```javascript

```

14. Buscar todos los libros con la palabra "Action" en el título.

```javascript

```

15. Buscar libros que pertenezcan a múltiples categorías $in

```javascript

```

16. Buscar libros que no pertenezcan a una categoría específica $nin

```javascript

```

17. Encontrá libros que NO sean de las categorías “Java” ni “MongoDB” $nor

```javascript

```

18. Buscá libros con campo publishedDate que sea de tipo date $type

```javascript

```

19. Actualizar múltiples documentos para establecer una misma clave usando $set (por ejemplo, disponibilidad en true).

```javascript

```

20. Renombrá el campo shortDescription a descripcionCorta $rename

```javascript

```

21. Buscar libros que tengan una cantidad de páginas entre 300 y 600 $gte $lte

```javascript

```

22. Buscar libros cuyos autores incluyan "Kyle Banker".

```javascript

```

23. Eliminar la categoría "Java" de un libro usando $pull

```javascript

```

24. Añadir un nuevo autor a un libro existente usando $push

```javascript

```

25. Buscar todos los libros que tienen más de un autor $size

```javascript

```

26. Encontrá libros que tengan exactamente dos categorías $size

```javascript

```

27. Buscar libros cuya descripción corta no esté vacía $ne

```javascript

```

28. Reemplazar completamente un libro por uno nuevo usando replaceOne.

```javascript

```

29. Buscar todos los libros que no tengan el campo thumbnailUrl ($exists y $ne).

```javascript

```

30. Buscar libros cuyo pageCount no esté entre 200 y 400 páginas $not

```javascript

```

31. Encontrá libros con exactamente 500 páginas $eq

```javascript

```

32. Buscá libros cuya categoría incluye tanto “Programming” como “Web” $all

```javascript

```

33. Multiplicá por 2 el número de páginas de un libro específico $mul

```javascript

```

34. Agregá un array comentarios y usá $push para añadir uno nuevo.

```javascript

```

35. Usá $addToSet para evitar agregar categorías duplicadas.

```javascript

```

36. Usá $pull para eliminar el autor “Desconocido” del array authors.

```javascript

```

37. Usá $elemMatch para encontrar libros con un comentario que tenga usuario: "Juan" y rating \>= 4

```javascript

```

38. Eliminá el campo thumbnailUrl de todos los documentos que lo tengan.

```javascript

```

39. Buscá libros donde descripcionCorta exista pero está vacía.

```javascript

```
