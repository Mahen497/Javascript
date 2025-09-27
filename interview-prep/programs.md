## To remove duplicates from an array in JavaScript, several methods can be employed.

```js
const originalArray = [1, 2, 2, 3, 4, 4, 5];
const uniqueArray = [...new Set(originalArray)];
console.log(uniqueArray); // Output: [1, 2, 3, 4, 5]
```
```js
const originalArray = [1, 2, 2, 3, 4, 4, 5];
const uniqueArray = originalArray.filter((item, index) => {
  return originalArray.indexOf(item) === index;
});
console.log(uniqueArray); // Output: [1, 2, 3, 4, 5]
```
---

## Sum of even/Odd digits

```js
const array = [1, 2, 3, 4, 5];

function sumOddArray(array) {
   const filterData = array.filter(item => item % 2 !== 0);
   return filterData.reduce((acc, itm) => acc + itm , 0 );
}
const result = sumOddArray(array);
console.log(result);
```

---

## String Duplication Remove

```js
const str = "aabbccdde";

const uniqueStr = str.split('').reduce((acc, char) => {
  return acc.includes(char) ? acc : acc + char;
}, '');

console.log(uniqueStr); // "abcde"
```

---


