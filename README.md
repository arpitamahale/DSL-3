# Practical No: 3
#  Aim: Write a python program to compute following computation on matrix:
#  1. Addition of two matrices 
# 2. Subtraction of two matrices 
# 3. Multiplication of two matrices 
# 4. Transpose of a matrix
# Program:-
A = []
B = []

def inp(m, rows, cols):
    for i in range(rows):
        a = []
        for j in range(cols):
            a.append(int(input(f"Enter element for row {i + 1}, col {j + 1}: ")))
        m.append(a)

def dis(matrix):
    for row in matrix:
        print(row)

def add(a, b, rows, cols):
    c = []
    for i in range(rows):
        row = []
        for j in range(cols):
            row.append(a[i][j] + b[i][j])
        c.append(row)
    print("\nADDITION MATRIX:")
    dis(c)

def sub(a, b, rows, cols):
    c = []
    for i in range(rows):
        row = []
        for j in range(cols):
            row.append(a[i][j] - b[i][j])
        c.append(row)
    print("\nSUBTRACTION MATRIX:")
    dis(c)

def mul(a, b, row_a, col_a, row_b, col_b):
    if col_a != row_b:
        print("\nMatrix multiplication not possible (columns of A != rows of B).")
        return
    c = [[0 for _ in range(col_b)] for _ in range(row_a)]
    for i in range(row_a):
        for j in range(col_b):
            for k in range(col_a):
                c[i][j] += a[i][k] * b[k][j]
    print("\nMULTIPLICATION MATRIX:")
    dis(c)

def trans(matrix, rows, cols):
    t = [[matrix[j][i] for j in range(rows)] for i in range(cols)]
    print("\nTRANSPOSED MATRIX:")
    dis(t)

print("FOR MATRIX A:")
row_a = int(input("Enter rows: "))
col_a = int(input("Enter cols: "))
inp(A, row_a, col_a)
dis(A)

print("\nFOR MATRIX B:")
row_b = int(input("Enter rows: "))
col_b = int(input("Enter cols: "))
inp(B, row_b, col_b)
dis(B)

while True:
    print("\n-------------")
    print("\n1: Addition\n2: Subtraction\n3: Multiplication\n4: Transpose\n5: Exit")
    ch = int(input("Enter your choice: "))

    if ch == 1:
        if row_a == row_b and col_a == col_b:
            add(A, B, row_a, col_a)
        else:
            print("Addition not possible (matrices have different dimensions).")
    elif ch == 2:
        if row_a == row_b and col_a == col_b:
            sub(A, B, row_a, col_a)
        else:
            print("Subtraction not possible (matrices have different dimensions).")
    elif ch == 3:
        mul(A, B, row_a, col_a, row_b, col_b)
    elif ch == 4:
        print("\n1: Transpose Matrix A\n2: Transpose Matrix B")
        n = int(input("Enter your choice: "))
        if n == 1:
            trans(A, row_a, col_a)
        elif n == 2:
            trans(B, row_b, col_b)
        else:
            print("Invalid choice.")
    elif ch == 5:
        print("End of Program")
        break
    else:
        print("Invalid choice. Please try again.")
# output:
# Enter row : 2
# Enter COL  : 2
# Enter element : 1
# Enter element : 2
# Enter element : 3
# Enter element : 4
# [1, 2]
# [3, 4]
# FOR MATRIX B

# Enter row : 2
# Enter COL : 2
# Enter element : 5
# Enter element : 6
# Enter element : 7
# Enter element : 8
# [5, 6]
# [7, 8]
# -------------
# 1:additon
# 2:substraction
# 3:multiplycation
# 4:transpose
# Enter your choice : 1

# ADDITION MATRIX
# [6, 8]
# [10, 12]

# -------------

# 1:additon
# 2:substraction
# 3:multiplycation
# 4:transpose
# Enter your choice : 2
# SUBRACTED MATRIX

# [-4, -4]
# [-4, -4]
# -------------
# 1:additon
# 2:substraction
# 3:multiplycation
# 4:transpose
# Enter your choice : 3
# !!!!!!ROW and COLUMN are matched !!!!!!
# [19, 22]
# [43, 50]
# -------------
# 1:additon
# 2:substraction
# 3:multiplycation
# 4:transpose
# Enter your choice : 4
# !!! WHICH MATRIX WANT TO TRANSPOSE
# 1:MATRIX A
# 2:MATRIX B
# ENTER = 1
# [1, 3]
# [2, 4]
