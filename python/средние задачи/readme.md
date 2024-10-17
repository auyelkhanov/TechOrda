1.Создайте программу, которая проверяет, является ли введенное пользователем число четным или нечетным, и выводит соответствующее сообщение.


2.Реализуйте программу, которая определяет, является ли введенная пользователем строка палиндромом (читается одинаково слева направо и справа налево). Выведите соответствующее сообщение.
s

3.Реализуйте программу, которая определяет, является ли заданное число простым (имеет только два делителя: 1 и само число). Выведите соответствующее сообщение.

4.Реализуйте программу, которая определяет, является ли заданная дата корректной (). Выведите соответствующее сообщение.
Дата дана в формате “20.01.2002”




5.Напишите программу для нахождения всех совершенных чисел (чисел, равных сумме своих делителей, исключая само число) в заданном диапазоне. Диапазон от 0 до 1000

6.Реализуйте программу для проверки, является ли заданное число числом Фибоначчи (число, которое является членом последовательности Фибоначчи). Заданное число 25

7.Напишите программу, которая определяет, является ли заданное число совершенным числом (число, равное сумме своих делителей, исключая само число). Выведите сообщение с результатом.

#1

n =int(input("Enter number: "))
if n % 2 == 0:
    print(f"The number {n} is even")
else:
    print(f"The number {n} is not event")

#2

s=input("Enter a string: ")
s = s.replace(" ","").lower()
if s == s[::-1]:
    print("The string is a palindrome")
else:
    print("The string is not a palindrome")

#3

def prime(a):
    if a <= 1:
        return False
    for i in range(2,a):
        if a % i == 0:
            return False
    return True
a=int(input("Enter number: "))
if prime(a):
    print(f"The number {a} is prime")
else:
    print(f"The number {a} is not prime")

#4

from datetime import datetime
def valid_date(data):
    try:
        date=datetime.strptime(data,"%d.%m.%Y")
        return True
    except ValueError:
        return False    
data=input("Enter date 'dd.mm.yyyy': ")
if valid_date(data):
    print (f"The date {data} is correct")
else:
    print (f"The date {data} is not correct")

#5 

def perfect_number(n):
    numbers = []
    for i in range(2,n+1):
        num = sum(j for j in range(1,i) if i % j == 0)       
        if num==i:
            numbers.append(i)
    return numbers
n=int(input())
numbers = perfect_number(n)
print (f"Perfect numbers in the range from 0 to {n}: {numbers}")

#6

def fibonacci(number):
    a,b = 0, 1
    while a <= number:
        if a == number:
            return True
        a, b = b, a+b
    return False
number =int(input("Enter number: "))
if fibonacci(number):
    print (f"The number {number} is fibonacci")
else:
    print(f"The number {number} is not fibonacci")

#7

def perfect_number(number):
    divisors =0
    for i in range(1,number):
        divisors+=i
    return divisors ==number
number=int(input("Enter number: "))
if perfect_number(number):
    print (f"The number {number} is perfect")
else:
    print (f"The number {number} is not perfect")

#8

def find_season(month,day):
    if (month==12 and day>=21) or (1<=month<=2) or (month==3 and day<21):
        return "Winter"
    elif (month==3 and day>=21) or (4<=month<=5) or (month==6 and day<21):
        return "Spring"
    elif (month==6 and day>=21) or (7<=month<=8) or (month==9 and day<23):
        return "Summer"
    elif (month==9 and day>=23) or (10<=month<=11) or (month==12 and day<21):
        return "Autumn"
month=int(input("Enter month(number): "))
day = int(input("Enter day: "))
season=find_season(month,day)
print (f"The Data {day}.{month} falls within the season: {season} ")


8.Создайте программу, которая определяет, в какой сезон года попадает заданная дата (месяц и день). 
