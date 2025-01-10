# luhn-algorithm
Verification of credit card number
# Luhn Algorithm

The **Luhn Algorithm** (also known as the **modulus 10** or **mod 10** algorithm) is a simple checksum formula used to validate various identification numbers, such as:

- Credit card numbers
- Debit card numbers
- IMEI (International Mobile Equipment Identity) numbers
- National Provider Identifier numbers (in healthcare)

## Purpose

The Luhn algorithm is used to verify the accuracy of identification numbers and detect simple errors like mistyped or incorrect digits.

---

## How the Luhn Algorithm Works

1. **Reverse the Number**  
   Start from the rightmost digit of the number and reverse the order of the digits.

2. **Double Every Second Digit**  
   Starting with the second digit from the right, double every second digit. If doubling a digit results in a number greater than 9, subtract 9 from the result.

3. **Sum the Digits**  
   Add all the digits together (both the doubled and the undoubled ones).

4. **Check the Sum**  
   If the total sum is a multiple of 10 (i.e., the remainder when divided by 10 is zero), the number is valid.

---

## Example: Validate a Credit Card Number

Let’s validate the number **4539 1488 0343 6467**.

1. **Reverse the Number**  
   `7 6 4 6 3 4 3 0 8 8 4 1 9 5 3 4`

2. **Double Every Second Digit**  
   Starting with the second digit from the right:
   - `7, 12, 4, 12, 3, 8, 3, 0, 16, 8, 8, 1, 18, 5, 6, 4`

   For numbers greater than 9 (e.g., 12, 16, 18), subtract 9:
   - `7, 3, 4, 3, 3, 8, 3, 0, 7, 8, 8, 1, 9, 5, 6, 4`

3. **Sum the Digits**  
   Add all the digits together:
   - `7 + 3 + 4 + 3 + 3 + 8 + 3 + 0 + 7 + 8 + 8 + 1 + 9 + 5 + 6 + 4 = 79`

4. **Check the Sum**  
   Since 79 is not a multiple of 10, the number is **invalid**.

---

## Applications

- Validating credit/debit card numbers during online transactions.
- Checking the validity of identification numbers without requiring a database lookup.
- Detecting accidental errors in typed numbers.

---

## Limitations

- The Luhn algorithm is not cryptographically secure and is only suitable for detecting errors, not for preventing fraud.
- It cannot detect all types of errors, such as transposition of two adjacent digits.
