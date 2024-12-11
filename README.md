# DSL-3
#Practical No: 3
#Aim: Write a python program to compute following computation on matrix:
#1. Addition of two matrices 
#2. Subtraction of two matrices 
#3. Multiplication of two matrices 
#4. Transpose of a matrix
#Program:-
A=[]
B=[]

def inp(m):
   for i in range(row):
     a=[]
     for j in range(col):
       a.append(int(input("Enter element : ")))
     m.append(a)


def dis(a):
 for i in a:
   print(i)

print("FOR MATRIX A \n")
row=int(input("Enter row : "))
col=int(input("Enter COL  : "))
inp(A)
dis(A)
print("FOR MATRIX B\n")
row1=int(input("Enter row : "))
col2=int(input("Enter COL : "))
inp(B)
dis(B)

def add(a,b):
  c=[]
  for i in range(row):
    ad=[]
    for j in range(col):
     ad.append(a[i][j]+b[i][j])
    c.append(ad)
  print("\nADDITION MATRIX \n")
  dis(c)

def sub(a,b):
  c=[]
  for i in range(row):
    ad=[]
    for j in range(col):
     ad.append(a[i][j]-b[i][j])
    c.append(ad)
  print("\nSUBRACTED MATRIX \n")
  dis(c)

def mul(a,b):
  C=[[0 for x in range(row)]for y in range(col)]
  for i in range(row):
    for j in range(col):
      for k in range(col):
        C[i][j]+=a[i][k]*b[k][j]
  dis(C)

def trans(a):
   T=[]
   for i in range(row):
      t=[]
      for j in range(col):
         t.append(a[j][i])
      T.append(t)
   dis(T)


while True:
  print("\n-------------\n \n1:additon\n2:substraction\n3:multiplycation\n4:transpose")
  ch=int(input("Enter your choice : "))
  if ch==1:
    add(A,B)
  elif ch==2:
    sub(A,B)
  elif ch==3:
    if(row==col2 and row1==col):
      print("\n\n!!!!!!ROW and COLUMN not matched !!!!!!\n\n")
    mul(A,B)
  elif ch==4:
    print("\n!!! WHICH MATRIX WANT TO TRANSPOSE\n1:MATRIX A \n2:MATRIX B")
    n=int(input("\nENTER = "))
    if n==1:
      trans(A)
    elif n==2:
      trans(B)
    else:
     break
  else:
    break
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
