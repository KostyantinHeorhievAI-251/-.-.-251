Завдання 1 - алгоритм сортування вибором

```python

def selection_sort(arr):
    n = len(arr)
    comparisons = 0
    assignments = 0

    print("Початковий масив:", arr)

    for i in range(n - 1):
        print(f"\nІтерація {i}:")
        print(f"поточний елемен: arr[{i}] = {arr[i]}")
        print(f"мінімальний елемент: {arr[i:]}")

        min_index = i
        assignments += 1

        for j in range(i + 1, n):
            comparisons += 1
            if arr[j] < arr[min_index]:
                min_index = j
                assignments += 1

        print(f"мінімальний елемент: arr[{min_index}] = {arr[min_index]}")

        comparisons += 1
        if min_index != i:
            print(f"Обмін arr[{i}] ({arr[i]}) і arr[{min_index}] ({arr[min_index]})")
            arr[i], arr[min_index] = arr[min_index], arr[i]
            assignments += 3
        else:
            print(f"Елемент arr[{i}] ({arr[i]}) вже знаходиться на своїй позиції")

        print(f"Масив після ітерації {i}: {arr}")

    print("Фінальний відсортований масив:", arr)
    print(f"Загальна кількість порівнянь: {comparisons}")
    print(f"Загальна кількість присвоєнь: {assignments}")
    return arr, comparisons, assignments


my_list = [69, 52, 97, 27, 10, 88, 29, 1, 24]
selection_sort(my_list.copy())

```

Завдання 2 - алгоритм сортування вставками

```python

def insertion_sort(arr):
    n = len(arr)
    comparisons = 0
    assignments = 0

    print("Початковий масив:", arr)

    for i in range(1, n):
        key = arr[i]
        assignments += 1
        j = i - 1
        assignments += 1

        print(f"\nІтерація {i}:")
        print(f"Елемент для вставки: {key}")
        print(f"Відсортована частина: {arr[:i]}")

        while j >= 0 and arr[j] > key:
            comparisons += 1
            print(f"Порівняння: {arr[j]} > {key}. True зсуваємо {arr[j]} вправо")
            arr[j + 1] = arr[j]
            assignments += 1
            j -= 1
            assignments += 1

        if j >= 0:
            comparisons += 1
            print(f"Порівняння: {arr[j]} > {key} false")
        else:
            print("Досягнуто початку масиву")

        arr[j + 1] = key
        assignments += 1
        print(f"Вставка {key} на позицію {j + 1}.")
        print(f"Масив після ітерації {i}: {arr}")

    print("Фінальний відсортований масив:", arr)
    print(f"Загальна кількість порівнянь: {comparisons}")
    print(f"Загальна кількість присвоєнь: {assignments}")
    return arr, comparisons, assignments


my_list = [69, 52, 97, 27, 10, 88, 29, 1, 24]
insertion_sort(my_list.copy())

```
