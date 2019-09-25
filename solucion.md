## Solución del ejercicio

* todos los comentarios

db.post.aggregate([{$unwind:"$comments"}, {$group:{"_id":{numero de usuario:"$by.user_id","nombre":"$by.name},"comments:{$sum:1}}}])

*comentarios

db.post.aggregate([{$unwind:"$comments"}, {$group:{"_id":{numero de usuario:"$.comments._id","nombre":"$comments.byname},"comments:{$sum:1}}}])

* 

db.post.aggregate([{$unwind:"$comments"}, {$group:{"_id":{"nombre":{"nombre":"$comments":$comments.by.name"},"comments":{$sum:1}}}, {$sort:{"comments":-1}}])

* Más comentario y menos comentarios

db.post.aggregate([{$unwind:"$comments"}, {$group:{"_id":{"nombre":{"nombre":"$comments":$comments.by.name"},"comments":{$sum:1}}}, {$sort:{"comments":-1},{$group:{_id:null,name_max:{$first:"$comments"},name_min:{$last:"$_id"}{"num_min":{$last:"$comments"}}}])

**
# ejercicio pagiación
https://codeday.me/es/qa/20190504/640419.html

db.restaurantes.find().skip(25).limit(25)

