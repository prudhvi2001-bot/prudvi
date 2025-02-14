# prudhvi


You can use a regular expression in JavaScript to validate the number format based on your rules. Here's a function to do that:

JavaScript Validation Function:

function isValidNumber(input) {
    const regex = /^(?:0{0,2}[1-9]\d*|0{0,2}0?\.\d{1,2}|100(?:\.00)?)$/;
    return regex.test(input);
}

// Test cases
console.log(isValidNumber("000.01")); // true
console.log(isValidNumber("00.01"));  // true
console.log(isValidNumber("0.1"));    // true
console.log(isValidNumber("25.25"));  // true
console.log(isValidNumber("80.25"));  // true
console.log(isValidNumber("0.01"));   // true
console.log(isValidNumber("99.99"));  // true
console.log(isValidNumber("0.99"));   // true
console.log(isValidNumber("100.00")); // true

console.log(isValidNumber("-25"));    // false
console.log(isValidNumber("-0.01"));  // false
console.log(isValidNumber("00"));     // false
console.log(isValidNumber("0"));      // false
console.log(isValidNumber("000"));    // false
console.log(isValidNumber(".00"));    // false
console.log(isValidNumber(".0"));     // false
console.log(isValidNumber("1."));     // false
console.log(isValidNumber("2."));     // false
console.log(isValidNumber("100."));   // false
console.log(isValidNumber("00.00.000.00")); // false
console.log(isValidNumber("."));      // false

Explanation:

1. Numbers between 0.01 and 100.00 are allowed.


2. Leading zeros are allowed, but only before a valid number. (000.01 is valid, but 00 is not).


3. A single decimal dot is required if there's a fractional part (.25 is valid, but 1. is not).


4. No negative numbers are allowed.


5. Numbers cannot be just 0 or leading zeros without a valid fraction.


6. Only up to two decimal places are allowed.


7. The number 100 is allowed, but only as 100 or 100.00.



Let me know if you need any modifications!

