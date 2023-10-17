# Спочатку визначимо наш вхідний масив, який буде мати розмірність NxN.
matrix = [
    [5, 2, 9],
    [8, 3, 7],
    [1, 4, 6]
]

# Декларуємо пустий список для зберігання сум кожної колонки.
column_sums = []

# За допомогою циклу пройдемося по кожній колонці і знайдемо суму чисел у ній.
for col in range(len(matrix[0])):
    column_sum = 0
    for row in range(len(matrix)):
        column_sum += matrix[row][col]
    column_sums.append(column_sum)

# Виведемо суми кожної колонки.
print("Суми колонок:", column_sums)

# Тепер відсортуємо колонки за зростанням.
sorted_matrix = []
for col in sorted(enumerate(matrix), key=lambda x: column_sums[x[0]]):
    sorted_matrix.append(col[1])

# Виведемо відсортований масив.
print("Відсортований масив:")
for row in sorted_matrix:
    print(row)
