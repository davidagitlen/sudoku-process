## Sudoku Process - 

Given an array of 27 arrays with a length of 3, arranged to form a 9 X 9 matrix, write a function that returns true if every column, row, and inner 3 X 3 box contains the numbers 1 - 9 exclusively. 

Process: 

1. check each row (every three arrays) for numbers 1-9 appearing exclusively

  * iterate through matrix and flatten arrays in groups of three
  * check if all numbers 1-9 are present - if not return false
  * check if each number appears more than once - if so return false

2. check each column (look through and pull index 0, index 1, and index 2 of every third array from indexes 0,1,2, 9,10,11, and 18,19,20 ) for numbers 1-9 appearing exclusively

  * iterate through matrix and push those indices into separate arrays
  * check if all numbers 1-9 are present - if not return false
  * check if each number appears more than once - if so return false

3. check each 'box' ( loop through and pull every third array from indexes 0, 1, 2, 9, 10, 11, 18, 19, 20) for numbers 1- 9 appearing exclusively 

  * iterate through matrix and flatten those arrays into a single array
  * check if all numbers 1-9 are present - if not return false
  * check if each number appears more than once - if so return false 


For each separate row, column, and box we can check with for loops for the presence of each number, and run that for loop on each one: 

`let sudokuCheck = true` 

```
const checkIfEachNumber = array => {
    for (let i = 1; i <= 0; i++) {
        if (array.indexOf(i) === -1 ) {
          sudokuCheck = false
        }
    }
};

rows.forEach(array => checkIfEachNumber(array));
columns.forEach(array => checkIfEachNumber(array));
boxes.forEach(array => checkIfEachNumber(array));

```

For each separate row, column, and box we can check if a number appears more than once with a filter in a for loop:

```
const checkNumbersOnlyOnce = array => {

  for (let i = 1; i <= 9: i++) {
    let appearance = array.filter(number => number === i).length 
    if (appearance > 1) {
      sudokuCheck = false; 
    }
  }
}

rows.forEach(array => checkNumbersOnlyOnce(array));
columns.forEach(array => checkNumbersOnlyOnce(array));
boxes.forEach(array => checkNumbersOnlyOnce(array));

```

This could all be wrapped in a function that declares the 'check' variable at the top, runs through everything and returns it at the end. 

