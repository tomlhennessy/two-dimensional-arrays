# Two Dimensional Arrays

* Definition: Arrays can contain other arrays as elements, forming a structure known as a two-dimensional array or a multidimensional array.
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

# Functions

## Two Dimensional Sum
Takes in a 2D array of numbers and returns the total sum of all numbers

```javascript
let twoDimensionalSum = function(arr) {
    // initialise sum to zero
    let sum = 0;

    // iterate over each element in outer array
    for (let i = 0; i < arr.length; i++) {
        // get current sub-array
        let subArr = arr[i];

        // iterate over each element in current sub-array
        for (let j = 0; j < subArr.length; j++) {
            // add current element to the sum
            sum += subArr[j];
        }
    }
    return sum;
}

let arr1 = [
    [1, 3],
    [-4, 7, 10],
    [2]
];
console.log(twoDimensionalSum(arr1)); // 19
```

## Max in Matrix
Takes in a 2D array and returns the largest value in the matrix.

```javascript
function maxInMatrix(matrix) {
    // initialise current max;
    let currentMax = -Infinity;

    // iterate over each row of matrix
    for (let row = 0; row < matrix.length; row++) {
        // iterate over each column of current row
        for (let col = 0; col < matrix[0].length; col++) {
            // check if current element is greater than current maximum.
            if (matrix[row][col]) > currentMax {
                // update currentMax
                currentMax = matrix[row][col];
            }
        }
    }
}

matrix = [[11,  2,-99],
          [20, 19, 10],
          [47, 72, 56]]

console.log(maxInMatrix(matrix)); // 72
```

## Max in Columns
Takes in a 2D array (matrix) and returns an array containing the max value in each column.

```javascript
function maxColumn(matrix) {
    // get the number of rows (height) and columns (width) in the matrix
    const height = matrix.length; // rows
    const width = matrix[0].length; // columns

    // initialise array to store max value for each column
    const maxColumns = [];

    // iterate over each column of matrix
    for (let col = 0; col < width; col++) {
        // initialised max value for current column with the first element of the column
        let colMax = matrix[0][col];

        // iterate over each row in the current column, starting from the second row
        for (let row = 1; row < height; row++) {
            if (matrix[row][col] > colMax) {
                // update current max if element is greater
                colMax = matrix[row][col];
            }
        }
        // after iterating over all rows in column, push max value of column into maxColumns array
        maxColumns.push(colMax);
    }
    // return array containing max value for each column
    return maxColumns;
}

// Example matrix
matrix = [
  [7,  4, 12],
  [9, 19,  3],
  [6, 21,  8]
];

// Call the maxColumn function with the example matrix
console.log(maxColumn(matrix)); // [12, 19, 21]
```

## Zip
Takes two arrays as input and returns a new array where each element is an array containing corresponding elements from the input arrays, paired together. If one array is longer than the other, the function only pairs elements up to the length of the shorter array.

```javascript
let zip = function(array1, array2) {
    // initialise empty array to store zipped pairs
    let zipped = [];
    // loop through indices of the first array
    for (let i = 0; i < array1.length; i++) {
        // get element at index 'i' from the first array
        let el1 = array1[i];
        // het element at index 'i' from the second array
        let el2 = array2[i];
        // push pair of elements into the zipped array
        zipped.push([el1, el2]);
    }
    return zipped;
}

console.log(zip([1, 2, 3, 4], ['eins', 'zwei', 'drei', 'vier'])); // Test with two arrays of equal length
// [ [ 1, 'eins' ], [ 2, 'zwei' ], [ 3, 'drei' ], [ 4, 'vier' ] ]
```
