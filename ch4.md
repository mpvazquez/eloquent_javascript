Chapter 4.3 Exercises

http://eloquentjavascript.net/code/#4.3

// Your code here.
function arrayToList(array, list) {
  if (!list) list = null;
  for (var i = array.length - 1; i >= 0; i--) {
    list = {value: array[i], rest: list};
  }
  return list;
}

function listToArray(list, arr) {
  if (!arr) arr = [];
  arr.push(list.value);
  if (list.rest) listToArray(list.rest, arr);
  return arr;
}

function prepend(value, list) {
	return arrayToList([value], list);
}

function nth(list, n) {
  var array = listToArray(list);
  return array[n];
}

console.log(arrayToList([10, 20]));
// → {value: 10, rest: {value: 20, rest: null}}
console.log(listToArray(arrayToList([10, 20, 30])));
// → [10, 20, 30]
console.log(prepend(10, prepend(20, null)));
// → {value: 10, rest: {value: 20, rest: null}}
console.log(nth(arrayToList([10, 20, 30]), 1));
// → 20