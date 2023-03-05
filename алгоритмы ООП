whole_numbers = input('Введите целые числа через пробел: ')
user_number = int(input('Введите любое число: '))

def is_int(str):
    str = str.replace(' ', '')
    try:
        int(str)
        return True
    except ValueError:
        return False

if " " not in whole_numbers:
    print("\nПри вводе отсутсвуют пробелы (введите числа согласно условиям ввода.)")
    whole_numbers = input('Введите целые числа через пробел: ')
if not is_int(whole_numbers):
    print('\nПри вводе содержатся не целые числа или недопустимые символы (введите числа согласно условиям ввода.)\n')
    print(error)
else:
    whole_numbers = whole_numbers.split()

# Преобразование в список

list_whole_numbers = [int(item) for item in whole_numbers]


# Сортировка списка по возрастанию

def merge_sort(L):
    if len(L) < 2:
        return L[:]
    else:
        middle = len(L) // 2
        left = merge_sort(L[:middle])
        right = merge_sort(L[middle:])
        return merge(left, right)

def merge(left, right):
    result = []
    i, j = 0, 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    while i < len(left):
        result.append(left[i])
        i += 1

    while j < len(right):
        result.append(right[j])
        j += 1
    return result


list_whole_numbers = merge_sort(list_whole_numbers)

# Установка позиции элемента

def binary_search(array, element, left, right):
    try:
        if left > right:
            return False
        middle = (right + left) // 2
        if array[middle] == element:
            return middle
        elif element < array[middle]:
            return binary_search(array, element, left, middle - 1)
        else:
            return binary_search(array, element, middle + 1, right)
    except IndexError:
        return 'Число выходит за диапазон списка, введите меньшее число.'


# Устанавливается номер позиции элемента, который меньше введенного пользователем числа, а следующий за ним больше или равен этому числу.

print(f'Список по возрастанию: {list_whole_numbers}')

if not binary_search(list_whole_numbers, user_number, 0, len(list_whole_numbers)):
    rI = min(list_whole_numbers, key=lambda x: (abs(x - user_number), x))
    ind = list_whole_numbers.index(rI)
    max_ind = ind + 1
    min_ind = ind - 1
    if rI < user_number:
        print(f'''В списке нет введенного элемента 
Ближайший меньший элемент: {rI}, его индекс: {ind}
Ближайший больший элемент: {list_whole_numbers[max_ind]} его индекс: {max_ind}''')
    elif min_ind < 0:
        print(f'''В списке нет введенного элемента
Ближайший больший элемент: {rI}, его индекс: {list_whole_numbers.index(rI)}
В списке нет меньшего элемента''')
    elif rI > user_number:
        print(f'''В списке нет введенного элемента
Ближайший больший элемент: {rI}, его индекс: {list_whole_numbers.index(rI)}
Ближайший меньший элемент: {list_whole_numbers[min_ind]} его индекс: {min_ind}''')
    elif list_whole_numbers.index(rI) == 0:
        print(f'Индекс введенного элемента: {list_whole_numbers.index(rI)}')
else:
    print(f'Индекс введенного элемента: {binary_search(list_whole_numbers, user_number, 0, len(list_whole_numbers))}')
