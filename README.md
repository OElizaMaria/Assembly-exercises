

Task 1 – Bitwise Properties

Odd numbers are detected using the AND 1 operation. If a number is odd, its least significant bit is 1, therefore number & 1 evaluates to 1.
To check whether a number is a power of two, the property n & (n - 1) is used. A power of two has exactly one bit set; subtracting 1 turns it into a sequence of 1s, and the AND operation yields 0 only in this case.

Task 2 – Date Validation and Sorting
2.1 Date Validation

The validation process checks:

Year validity

Month validity

Day validity based on the month

Months with 30 days and February are treated as special cases. If all checks pass, the day is verified to be within the range [1, 31].

2.2 Sorting Records

Records are first sorted by a validity flag. If flags are equal, sorting continues by year, month, and day.
If two records represent the same date, names are compared using a custom byte-by-byte implementation of strcmp.
Swapping is performed byte by byte.

Task 3 – Base64 Encoding

The main challenge was handling byte-level operations. The movzx instruction is used frequently to safely move bytes into 32-bit registers.
The algorithm processes input in blocks of three bytes, following the Base64 encoding steps.
An alphabet table is provided in the data section.
To extract 6-bit groups, the operation AND reg, 63 is used, where 63 represents six consecutive 1 bits.

Task 4 – Sudoku Validation
Row Check

Each row is first checked for invalid values (numbers less than 1 or greater than 9).
Duplicates are then detected using two nested loops.

Column Check

Instead of duplicate scanning, column values are sorted using bubble sort.
Duplicates become adjacent and are detected through a final linear pass.

Box Check

The starting index of the 3×3 box is computed from the given index.
A garbage check is performed first.
Duplicate detection is adapted from the row-check logic, with manual row transitions inside the box achieved by adding 6 to the pointer (given a 9×9 grid).
A counter tracks repeated values; more than two occurrences indicate a duplicate.
