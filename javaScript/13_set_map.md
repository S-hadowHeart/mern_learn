## SET 

var emptySet = new Set ()

console.log(emptySet.size)


var myArray = [1,2,3,4,2]
var newSet = new Set(myArray)

console.log(newSet)

newSet.add(2)
console.log(newSet)
newSet.add(5)
console.log(newSet)

console.log(newSet.has(9))

newSet.clear()
