## Solución del ejercicio

db.post.aggregate([{$unwind:"$commentes"}, {$group:{"_id":"$by.user_id"}}])
