# DSL-2
                                                                Practical No: 2 
Problem Statement: Write a Python program that computes the net amount of a bank account based a transaction log from console input. The transaction log format is shown as following: D 100 W 200 (Withdrawal is not allowed if balance is going negative. Write functions for withdraw and deposit) D means deposit while W means withdrawal. Suppose the following input is supplied to the program: D 300, D 300 , W 200, D 100 Then, the output should be: 500
Program:-
def deposit(amt):
    global balance
    balance=balance+amt

def withdral(amt):
    global balance
    if(amt > balance):
        print("insuffecient balance")
    else:
        balance=balance-amt

list1 = []
balance = 0
print("Enter Transaction log")

while True:
    data = input()
    if (data==""):
        break

    list1.append(data.split())

for transaction in list1:
    if (transaction[0]=="d"):
        deposit(int(transaction[1]))
    elif (transaction[0]=="w"):
        withdral(int(transaction[1]))
    else:
        print("error")
print("total balaance :" ,balance)
output:
Enter Transaction log
d 1000
w 300

total balaance : 700
