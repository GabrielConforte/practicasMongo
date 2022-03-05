# practicasMongo

> db.productos.count()
> db.mensaje.count()

//insertamos un producto

> db.productos.insertOne({
...     "title":"Dinosaurio de plastico",
...     "description":"ipsum dolorem",
...     "timestamp":"DD/MM/YY",
...     "price":500,
...     "thumbnail":" ",
...     "id":2,
...     "stock":100,
...     "codigo":"335"
...     })

//consulto por un producto

> db.productos.find({"title":"Dinosaurio de plastico"})

//Busquedas filtradas

> db.productos.find({"price":{"$lt":1000}});
> db.productos.find({"price":{"$gt":1000,"$lt":3000}});
> db.productos.find({"price":{"$gt":3000}});
> db.productos.find({},{"title":1}).sort({"price":1}).limit(1).skip(3).pretty({"title"})

//Actualizacion

> db.productos.updateMany({"price":{"$gt":0}},{$set: {"stock":100}})
> db.productos.updateMany({"price":{"$gt":4000}},{$set: {"stock":0}})

//Borrar

> db.productos.deleteMany({price:{$lt:1000}})

//Crear usuario

> db.createUser(
...   {
...     user: "Pepe",
...     pwd: "asd456",
...     roles: [
...        { role: "read", db: "ecommerce" }
...     ]
...   }
... )

> mongo -u Pepe -p asd
> db.productos.find()
