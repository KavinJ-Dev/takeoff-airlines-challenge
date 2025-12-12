# Challenge Creation - TakeOff Airlines

## Description:

You are a junior software engineer at TakeOff Airlines, working on the internal system that assigns seats to passengers during the booking process. Recently, the customer support team has reported unusual issues:

- Some passengers are being assigned duplicate seats
- Some seat assignments show up out of order
- And occasionally, invalid or corrupted seat numbers appear in the logs

Your team lead has asked you to investigate and fix the data quality issue affecting the seat assignment system.

### Main Task:
Build a safe and reliable function that processes raw seat assignment data and returns only valid seats, sorted and deduplicated.

### Requirements:

1. Remove invalid seat numbers

    - Valid seats are integers from 1 to 300 (our aircraft has 300 seats)
    - Ignore anything outside that range (e.g., 0, 301, -5, 999)
    - Ignore non-integer values entirely (e.g., strings, decimals, null, etc.)

2. Remove duplicates

    - If the same seat number appears multiple times, keep only one copy

3. Return the cleaned seat list in sorted order

    - Sort from lowest seat number to highest

### Example:
Input:  [150, 25, 150, 301, 25, 0, 1, "ABC", 3.5, null, 300]
Output: [1, 25, 150, 300]

### Explanation:
- 150 appears twice → kept once
- 25 appears twice → kept once
- 301 is invalid (too high)
- 0 is invalid (too low)
- "ABC" is invalid (not a number)
- 3.5 is invalid (not an integer)
- null is invalid (not a number)
- Result is sorted: [1, 25, 150, 300]

### Hints:
Think about edge cases: What if the input is empty? What if all entries are invalid?
- Validation first: Check each seat to make sure it's a valid integer between 1 and 300
- Data structures: Some data structures automatically handle duplicates—consider using them
- Type checking: Make sure you're working with actual numbers, not strings or other types
