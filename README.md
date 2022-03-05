# practicasMongo

## inicializamos
    mongo
    use ecommerce
##  creo y lleno las colecciones
    db.productos.insertMany([{
    "title":"Escuadra",
    "description":"Texto Editado",
    "timestamp":"DD/MM/YY",
    "price":"100",
    "thumbnail":"https://cdn3.iconfinder.com/data/icons/education-209/64/ruler-triangle-stationary-school-256.png",
    "id":1,
    "stock":"100",
    "codigo":"321"
    }
    ,{
    "title":"Dinosaurio de plastico",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":500,
    "thumbnail":" ",
    "id":2,
    "stock":100,
    "codigo":"335"
    },{
    "title":"Regla",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":150,
    "thumbnail":" ",
    "id":3,
    "stock":323,
    "codigo":"310"
    },{
    "title":"Lapiz",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":100,
    "thumbnail":" ",
    "id":4,
    "stock":100,
    "codigo":"324"
    },{
    "title":"Calculadora Cientifica",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":5000,
    "thumbnail":" ",
    "id":5,
    "stock":100,
    "codigo":"325"
    },{
    "title":"Lapicera",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":150,
    "thumbnail":" ",
    "id":6,
    "stock":100,
    "codigo":"326"
    },{
    "title":"Relog Calculadora",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":1500,
    "thumbnail":" ",
    "id":7,
    "stock":100,
    "codigo":"327"
    },{
    "title":"Cartuchera",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":700,
    "thumbnail":" ",
    "id":8,
    "stock":100,
    "codigo":"328"
    },{
    "title":"Goma de borrar",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":400,
    "thumbnail":" ",
    "id":9,
    "stock":100,
    "codigo":"329"
    },{
    "title":"Cutter",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":200,
    "thumbnail":" ",
    "id":10,
    "stock":100,
    "codigo":"330"
    }])
    
## 
    db.mensaje.insertMany([{
    "email":"conforte_gabriel@outlook.com", mensaje":"Hola, vendes zapatos?",
     "id":"1","date":"DD/MM/YY"},
    {"email":"admin@mail.com",
    "mensaje":"no, señor esto es una fabrica de pastas",
    "id":"2","date":"DD/MM/YY"},
    {"email":"conforte_gabriel@outlook.com",
    "mensaje":"Y sandandalias?",
    "id":"3","date":"DD/MM/YY"},
    {"email":"admin@mail.com",
    "mensaje":"no, señor, ya le dije! esto es una fabrica de pastas",
    "id":"4","date":"DD/MM/YY"},
    {"email":"admin@mail.com",
    "mensaje":"Señor, creo que no vamos a seguir con este chat",
    "id":"5","date":"DD/MM/YY"},
    {"email":"conforte_gabriel@outlook.com",
    "mensaje":"Perdon, no queria ofenderlos. Pero le puedo hacer otra consulta",
    "id":"6","date":"DD/MM/YY"},
    {"email":"admin@mail.com",
    "mensaje":"Que?",
    "id":"7","date":"DD/MM/YY"},
    {"email":"conforte_gabriel@outlook.com",
    "mensaje":"Tienen calzones?",
    "id":"8","date":"DD/MM/YY"},
    {"email":"admin@mail.com",
    "mensaje":"vaya, eso si tenemos",
    "id":"9","date":"DD/MM/YY"},
    {"email":"conforte_gabriel@outlook.com",
    "mensaje":"Genial enviame uno",
    "id":"10","date":"DD/MM/YY"})

## listamos las colecciones
    db.productos.find()
    db.mensaje.find()

## Muestro la cantidad de articulos en las colecciones
    db.productos.count()
    db.mensaje.count()
    
## insertamos un producto nuevo
    db.productos.insertOne({
     "title":"Dinosaurio de plastico",
    "description":"ipsum dolorem",
    "timestamp":"DD/MM/YY",
    "price":500,
    "thumbnail":" ",
    "id":2,
    "stock":100,
    "codigo":"335"
     })

## consulto por un producto
    db.productos.find({"title":"Dinosaurio de plastico"})

## Realizo consultas avanzadas
    db.productos.find({"price":{"$lt":1000}});
    db.productos.find({"price":{"$gt":1000,"$lt":3000}});
    db.productos.find({"price":{"$gt":3000}});
    db.productos.find({},{"title":1}).sort({"price":1}).limit(1).skip(3).pretty({"title"})

## Actualizamos algunos datos
    db.productos.updateMany({"price":{"$gt":0}},{$set: {"stock":100}})
    db.productos.updateMany({"price":{"$gt":4000}},{$set: {"stock":0}})

## Borrar
    db.productos.deleteMany({price:{$lt:1000}})


## Crear usuario
    db.createUser(
     {
     user: "Pepe",
     pwd: "asd456",
     roles: [
     { role: "read", db: "ecommerce" }
     ]
     }
     )

##  
    mongo -u Pepe -p asd456

##
    db.ecommerce.find()
