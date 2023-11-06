# lab5
#1 

a = input("строка: ")

char_list = list(a.lower())

print("список:")
print(char_list)
#2
char_list = ['p', 'u', 'l', 'p', ' ', 'f', 'i', 'c', 't', 'i', 'o', 'n']

list_count = []

for char in char_list:
    
    found = False
    for a in list_count:
        if a[0] == char:
            a[1] += 1
            found = True
            break

    if not found:
        list_count.append([char, 1])

tuples = [(a[0], a[1]) for a in list_count]

print(tuples)
#3 
a_l = [('p', 2), ('u', 1), ('l', 1), (' ', 1), ('f', 1), ('i', 2), ('c', 1), ('t', 1), ('o', 1), ('n', 1)]

l_vow = []
l_cons = []
l_sym = []

vowels = "aeiouAEIOU"

for char, count in a_l:
    if char in vowels:
        l_vow.append((char, count))
    elif char.isalpha():
        l_cons.append((char, count))
    else:
        l_sym.append((char, count))

print("Гласные =", l_vow)
print("Согласные =", l_cons)
print("Символы =", l_sym)
#4 
list_A = [1, 5, 8, 7, 9, 6, 7, 5, 8, 3, 9, 10, 2, 1, 3, 4]

list_A.sort()

n = len(list_A)
q1 = list_A[:n // 4]
q2 = list_A[n // 4:(n // 4) * 2]
q3 = list_A[(n // 4) * 2:(n // 4) * 3]
q4 = list_A[(n // 4) * 3:]

if n % 4 != 0:
    num_zeros = 4 - (n % 4)
    q1 = [0] * num_zeros + q1

print("q1 =", q1)
print("q2 =", q2)
print("q3 =", q3)
print("q4 =", q4)
#2.1

student_n = 'Adam'
assignment_result = [82, 56, 44, 30]
lab_result = [78.20, 77.20]
test_result = [78, 77]

student = {
    'name': student_n,
    'assignment': assignment_result,
    'test': test_result,
    'lab': lab_result
}

print(student)
#2.2
student = {'name': 'Adam', 'assignment': [82, 56, 44, 30], 'test': [78, 77], 'lab': [78.2, 77.2]}

total_subm = len(student.get('assignment', [])) + len(student.get('lab', [])) + len(student.get('test', []))

submission_check = {student['name']: total_subm}

print(submission_check)
#2.3
s1 = {'name': 'Adam', 'assignment': [82, 56, 44, 30], 'test': [78, 77], 'lab': [78.2, 77.2]}
submission_rate = {'Adam': 6}

if submission_rate.get(s1['name'], 0) >= 4:
    assignment_avg = sum(s1['assignment']) / len(s1['assignment'])
    lab_avg = sum(s1['lab']) / len(s1['lab'])
    test_avg = sum(s1['test']) / len(s1['test'])
    final_grade = 0.3 * assignment_avg + 0.5 * lab_avg + 0.2 * test_avg
    s1['final_grade'] = final_grade
else:
    s1['final_grade'] = 0

print(s1)

s2 = {'name': 'Kevin', 'assignment': [82, 30], 'test': [], 'lab': [78.2]}
submission_rate = {'Adam': 6, 'Kevin': 3}

if submission_rate.get(s2['name'], 0) >= 4:
    assignment_avg = sum(s2['assignment']) / len(s2['assignment'])
    lab_avg = sum(s2['lab']) / len(s2['lab'])
    test_avg = sum(s2['test']) / len(s2['test'])
    final_grade = 0.3 * assignment_avg + 0.5 * lab_avg + 0.2 * test_avg
    s2['final_grade'] = final_grade
else:
    s2['final_grade'] = 0

print(s2)
#2.4
s1 = {'name': 'Adam', 'assignment': [82, 56, 44, 30], 'test': [78, 77], 'lab': [78.2, 77.2], 'final_grade': 70.25}
s2 = {'name': 'Kevin', 'assignment': [82, 30], 'test': [], 'lab': [78.2], 'final_grade': 0}

students = {s1['name']: s1, s2['name']: s2}

print(students)
#3 
transactions = [(1001, 2), (1001, 1), (1003, 2), (1005, 2), (1001, 3), (1007, 1), (1007, 2), (1100, 2), (1003, 2), (1001, 1)]

stats = {}

for user_id, transaction_type in transactions:
    if user_id not in stats:
        stats[user_id] = {1: 0, 2: 0, 3: 0}

    stats[user_id][transaction_type] += 1

for user_id in stats:
    most_frequent_transaction = max(stats[user_id], key=stats[user_id].get, default=None)
    least_frequent_transaction = min(stats[user_id], key=stats[user_id].get, default=None)
    stats[user_id]['mft'] = most_frequent_transaction
    stats[user_id]['lft'] = least_frequent_transaction

print("stats =", stats)
