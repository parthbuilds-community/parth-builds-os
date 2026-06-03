# Big O Notation Explained Simply

## What is Big O?
- Measures how algorithm performance scales with input size
- Not about actual speed (seconds), about growth rate
- Helps compare algorithms objectively
- Ignore constants and smaller terms

## Common Complexities (Best to Worst)

### O(1) - Constant Time
- Same time regardless of input size
- **Examples:** Array access by index, hash map lookup
- **Code:** `array[5]` or `dictionary['key']`

### O(log n) - Logarithmic Time
- Divides problem in half each step
- **Examples:** Binary search in sorted array
- **Growth:** Very slow, efficient for large datasets

### O(n) - Linear Time
- Time grows proportionally with input
- **Examples:** Single loop through array, simple search
- **Code:** `for item in array: print(item)`

### O(n log n) - Linearithmic Time
- Common in efficient sorting algorithms
- **Examples:** Merge sort, quick sort (average case)
- **Growth:** Faster than O(n²), slower than O(n)

### O(n²) - Quadratic Time
- Time grows with square of input size
- **Examples:** Nested loops, bubble sort
- **Code:** 
```python
for i in array:
    for j in array:
        # do something
```

### O(2ⁿ) - Exponential Time
- Doubles with each additional input
- **Examples:** Recursive Fibonacci (naive), subset generation
- **Growth:** Gets slow very fast

## Quick Tips
- Nested loops = multiply complexities
- Drop constants: O(2n) becomes O(n)
- Keep highest term: O(n² + n) becomes O(n²)
- Space complexity uses same notation

## 🤝 Contributing

Found an amazing resource? Want to add your favorite course? Check out our [CONTRIBUTING.md](../CONTRIBUTING.md) to learn how you can help grow this collection!

## 🔗 Connect With Me

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/parth.builds)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/parthnarkar)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/parthnarkar)
[![LeetCode Profile](https://img.shields.io/badge/LeetCode-ParthNarkar-FFA116?style=for-the-badge&logo=leetcode)](https://leetcode.com/u/parthnarkar/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:parthnarkarofficial@gmail.com)
[![Twitter](https://img.shields.io/badge/-Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/parthnarkar)
[![Discord](https://img.shields.io/badge/-Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/users/parth_narkar)

### ⭐ Found this helpful? Give this Repo a STAR!

[![parth-builds-os Github Repo Footer](https://github.com/user-attachments/assets/4bef3a04-16ee-4484-a52c-4f31182e1916)](https://github.com/parthnarkar/parth-builds-os)
