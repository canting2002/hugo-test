---
title: "Assignment1"
date: 2025-06-22
draft: false
---

# Matrix Multiplication Project Report

**Student Name**: wu canting  
**Student ID**: ZY2457B09  
**Submission Date**: 2025/3/26


## System Configuration

｜canting｜output｜
｜————｜————｜
｜CPU Model｜ Apple M2｜
｜Memory Size｜ 8 GB｜
｜Operating System Version｜ 11881.81.4｜
｜Compiler Version｜ Apple clang version 17.0.0 (clang-1700.0.13.3)｜
｜Python Version｜ Python 3.13.1｜

## Implementation Details

### C Language Implementation


### Python Language Implementation
-  **Source Code**: Include the Python script with comments explaining key sections. 
def multiply_matrices(A, B):
    if not (is_valid_matrix(A) and is_valid_matrix(B)):
        raise ValueError("输入必须是有效矩阵（各行长度一致）")
    if len(A[0]) != len(B):
        raise ValueError("矩阵 A 的列数必须等于矩阵 B 的行数！")

    rows_A, cols_A = len(A), len(A[0])
    rows_B, cols_B = len(B), len(B[0])
    result = [[0 for _ in range(cols_B)] for _ in range(rows_A)]

    for i in range(rows_A):
        for j in range(cols_B):
            for k in range(cols_A):  # 或 len(B)
                result[i][j] += A[i][k] * B[k][j]
    return result

def is_valid_matrix(matrix):
    return all(len(row) == len(matrix[0]) for row in matrix) if matrix else False

def print_matrix(matrix):
    for row in matrix:
        print("\t".join(map(str, row)))

def main():
    matrix_A = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ]
    matrix_B = [
        [11, 12, 13],
        [21, 22, 23],
        [31, 32, 33]
    ]

    try:
        result = multiply_matrices(matrix_A, matrix_B)
        print("Matrix A:")
        print_matrix(matrix_A)
        print("\nMatrix B:")
        print_matrix(matrix_B)
        print("\nResult (A × B):")
        print_matrix(result)
    except ValueError as e:
        print(f"错误: {e}")

if __name__ == "__main__":
    main()


## Algorithm Verification
-  **Correctness**: 
def test_random_matrix():
    A = np.random.randint(0, 10, size=(3, 3)).tolist()
    B = np.random.randint(0, 10, size=(3, 3)).tolist()
    C_custom = multiply_matrices(A, B)
    C_ref = np.dot(A, B).tolist()
    assert C_custom == C_ref, "结果与 NumPy 不一致"

## Conclusion
Markdown offers significant convenience in document writing, as it allows users to quickly generate desired formats by inputting simple syntax code. Additionally, Markdown files are lightweight and can be opened and accessed with ease and speed.

## References
- **GeeksforGeeks C language Programming Tutorial**  https://www.geeksforgeeks.org/c-programming-language/
- **Python Official Documentation (Version 3.x)**   https://docs.python.org/3/
## Appendix
-  **Additional Notes**: Include any additional notes or observations made during the project.
