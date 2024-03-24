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

## Zany Zip
Accepts two arrays as arguments. Function should return a 2D array with subarrays of length of 2 that contain elements at corresponding indices from the input arrays. If one of the arrays is shorter than the other, then substitute null for the missing elements.

```javascript
let zanyZip = function(array1, array2) {
    // create empty array to store the elements
    let zipped = [];

    // iterate through arrays using a for loop
    // stopping when either array1 or array2 is exhausted
    for (let i = 0; i < array1.length || i < array2.length; i++) {
        // get the current element from array1 and array2
        let el1 = array1[i];
        let el2 = array2[i];

        // if the element from array1 is undefined (array1 is shorter),
        // replace it with null
        if (el1 === undefined) {
            el1 = null;
        }

        if (el2 === undefined) {
            el2 = null;
        }

        // push elements from array1 and array2 into zipped array
        zipped.push([el1, el2]);
    }

    return zipped;
}

console.log(zanyZip([1, 2, 3, 4], ['eins', 'zwei', 'drei']));
// [ [ 1, 'eins' ], [ 2, 'zwei' ], [ 3, 'drei' ], [ 4, null ] ]
```

## Matrix Addition
Performs matrix addition by adding corresponding elements from two matrices 'm1' and 'm2'. It iterates through each element of the matrices, adds them together, and stores the result in a new matrix called 'sum'.

```javascript
let matrixAddition = function(m1, m2) {
    // create empty array to store sum of the matrices
    let sum = [];

    // iterate through each row of the matrices using for loop
    for (let row = 0; row < m1.length; row++) {
        // create temporary array to store elements of current row
        let subArray = [];

        // iterate through each column of the matrices using nested for loop
        for (let col = 0; col < m1[0].length; col++) {
            // add corresponding elements of m1 and m2 and push the result
            subArray.push(m1[row][col] + m2[row][col]);
        }

        // push temporary array (representing a row of the resulting matrix)
        // into the sum array
        sum.push(subArray);
    }
    // return sum matrix
    return sum;
}

let matrixA = [[2,5], [4,7]]
let matrixB = [[9,1], [3,0]]
let matrixC = [[-1,0], [0,-1]]
let matrixD = [[2, -5], [7, 10], [0, 1]]
let matrixE = [[0 , 0], [12, 4], [6,  3]]

console.log(matrixAddition(matrixA, matrixB)); // [[11, 6], [7, 7]]
console.log(matrixAddition(matrixA, matrixC)); // [[1, 5], [4, 6]]
```

## Lucky Numbers
Takes a 2D array (matrix) as input and returns an array containing all the lucky numbers. It first finds the minimum element in each row and stores it in the 'minInRows' array. Then it finds the maximum element in each column and stores it in the 'maxInCols' array. Finally it checks if the minimum element in a row is also the maximum element in its column, and if so, adds it to the array of lucky numbers.

```javascript
function luckyNumbers(matrix) {
    // initialise arrays to store min elements in rows and max in columns
    let minInRows = [];
    let maxInCols = [];

    // iterate through each row of the matrix
    for (let i = 0; i < matrix.length; i++) {
        // find minimum element in current row
        let minRow = Math.min(...matrix[i])
        minInRows.push(minRow); // store minimum element in array

        // iterate through each column of matrix
        for (let j = 0; j < matrix[i].length; j++) {
            // if maxInCols[j] is not defined or smaller than current element, update it
            if (maxInCols[j] === undefined || maxInCols[j] < matrix[i][j]) {
                maxInCols[j] = matrix[i][j];
            }
        }
    }

    // initialise an array to store lucky numbers
    let luckyNumbers = [];

    // check if minimum element in a row is also the max in its column
    for (let i = 0; i < matrix.length; i++) {
        for (let j = 0; j < matrix[i].length; j++) {
            if (minInRows[i] === maxInCols[j]) {
                // if condition is met, add the lucky number to the result array
                luckyNumbers.push(minInRows[i]);
            }
        }
    }
    return luckyNumbers;
}

matrix = [[ 5,  9, 21],
          [ 9, 19,  6],
          [12, 14, 15]]

console.log(luckyNumbers(matrix)); // [12]

matrix = [[ 5, 10,  8,  6],
          [10,  2,  7,  9],
          [21, 15, 19, 10]]

console.log(luckyNumbers(matrix)); // [10]
```

## Spiral Matrix
Takes in a 2D array (matrix) and returns an array containing the elements in spiral order.

```javascript
function spiralOrder(matrix) {
    if (matrix.length === 0) return []; // return empty array if matrix is empty

    let result = []; // intiialise array to store elements in spiral order

    let top = 0; // intialise top row index
    let bottom = matrix.length - 1; // initalise bottom row index
    let left = 0; // initialise left column index
    let right = matrix[0].length - 1; // intialise right column index

    while (top <= bottom && left <= right) {
        // traverse from left to right on the top row
        for (let i = left; i <= right; i++) {
            result.push(matrix[top][i]);
        }
        top++; // move to next row

        // traverse from top to bottom on the rightmost column
        for (let i = top; i <= bottom; i++) {
            result.push(matrix[i][right]);
        }
        right --; // move to previous column

        // check if top has crossed bottom or left has crossed right
        if (top <= bottom && left <= right) {
            // traverse from right to left on bottom row
            for (let i = right; i >= left; i--) {
                result.push(matrix[bottom][i]);
            }
            bottom--; // move to previous row

            // traverse from bottom to top on leftmost column
            for (let i = bottom; i >= top; i--) {
                result.push(matrix[i][left]);
            }
            left++; // move to next column
        }
    }
    return result;
}

matrix = [[ 1, 2, 3],
          [ 4, 5, 6],
          [ 7, 8, 9]]

console.log(spiralOrder(matrix)); // [1,2,3,6,9,8,7,4,5]

matrix = [[1, 2, 3, 4],
          [5, 6, 7, 8],
          [9,10,11,12]]


console.log(spiralOrder(matrix)); // [1,2,3,4,8,12,11,10,9,5,6,7]
```

## Pyramid Array
Takes in an array of numbers representing the base of a pyramid. function should return a 2D array representing the completed pyramid. To generate an element of the next level of the pyramid, we sum the elements below and to the left and below and to the right.

```javascript
// helper function: adjacentSums
// calculates the sums of adjacent elements in an array
let adjacentSums = function(arr) {
    let sums = []; // initialise an array to store the sums
    // iterate through an array up to the second-to-last element
    for (let i = 0; i < arr.length - 1; i++) {
        let sum = arr[i] + arr[i + 1]; // calculate the sum of adjacent elements
        sums.push(sum); // add the sum to the sums array
    }
    return sums; // return the array of sums
}

// main function: pyramidArray
// this function constructs a pyramid array based on a given base array
let pyramidArray = function(base) {
    let pyramid = [base]; // initialise the pyramid array with the base array
    // continue until the pyramid array reaches desired size
    while (pyramid.length < base.length) {
        // get adjacent sums of the first row of pyramid
        let next = adjacentSums(pyramid[0]);
        // add the sums as a new row at beginning of the pyramid array
        pyramid.unshift(next);
    }
    return pyramid;
}

// For example, given 2, 3, 7, 5, 9 as the base, we should construct this pyramid:
//
//           85
//         37  48
//       15  22  26
//    5   10   12   14
//  2   3    7    5    9
```

## Pascal's Triangle
Generates Pascal's triangle up to a specified height by iteratively calculating each row based on the previous row.

```javascript
let pascalsTriangle = function(height) {
    // initialise Pascal's triangle with the first row
    let triangle = [[1]];

    // continue adding rows until the desired height is reached
    while (triangle.length < height) {
        // get last row added to triangle
        let last = triangle[triangle.length - 1];

        // initialise next row with 1 (first element always 1)
        let next = [1];

        // iterate through elements of last row
        for (let i = 0; i < last.length - 1; i++) {
            // calculate each element by adding current element and next element
            next.push(last[i] + last[i + 1]);
        }

        // add 1 to end of next row (last element always 1)
        next.push(1);

        // add newly calulated row to Pascal's triangle
        triangle.push(next);
    }
    return triangle;
}

console.log(pascalsTriangle(5));
// [
//     [1],
//     [1, 1],
//     [1, 2, 1],
//     [1, 3, 3, 1],
//     [1, 4, 6, 4, 1]
// ]
```
