const regex = /^(?!0+(?:\.0+)?$)(?:0?\d{0,2}|\d{1,2})(?:\.\d+)?$/;

function isValidNumber(input) {
    return regex.test(input) && parseFloat(input) >= 0.01 && parseFloat(input) <= 100;
}

// Test cases
const testCases = [
    "0.01", "000.01", "0.1", "00.01", ".25", "12.34", "89.98", "99.99", "100.00", 
    "00", "0", "000", "000.00", "0.0", "00.0", "000.", "0.", ".", "2.", "3."
];

testCases.forEach(num => {
    console.log(`${num}: ${isValidNumber(num)}`);
});
