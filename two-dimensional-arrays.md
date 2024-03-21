# Two Dimensional Arrays

* Definition: Arraus can contain other arrays as elements, forming a structure known as a two-dimensional array or a multidimensional array.
* Accessing Elements: To access elements within a 2D array, use double indices, where the first index refers to the row and the second index refers to the column.

```javascript
let twoDimensional = [
    ["a", "b", "c"],
    {"d", "e"},
    ["f", "g", "h"]
]

console.log(twoDimensional[1]); // [ 'd', 'e' ]
console.log(twoDimensional[0][2]); // 'c'
```

* Iterating Through: To iterate through a 2D array, utilise nested loops, with the outer loop iterating over rows and the inner loop iterating over columns.

```javascript
let array = [["a", "b", "c"], ["d", "e"], ["f", "g", "h"]];

for (let i = 0; i < array.length; i++) {
    let subArray = array[i];

    for (let j = 0; j < subArray.length; j++) {
        console.log(subArray[j]);
    }
}
```

## Practical Applications:

* Grid Representations: 2D arrays are commonly used to represent grids in various applications such as chess-boards, sudoku puzzles, and spreadsheet software like Excel.
* Iterating Through: Nested loops are used to efficiently traverse and manipulate the elements of a 2D array.

## Key Takeaways:

* Arrays can contain arrays as elements, forming 2D arrays.
* Iterating through 2D arrays requires nested loops, with the outer loop for rows and the inner loop for columns.
