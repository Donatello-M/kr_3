### Задание 1

Объясните, для чего в языке Си используется динамическая память и в каких ситуациях статического выделения памяти становится недостаточно. В чем заключается главное различие между функциями malloc() и calloc() при выделении памяти под массив? Что будет находиться в памяти в обоих случаях до записи туда реальных данных?

### Задание 2

Опишите результат выполнения функции ниже:
```c
#include <stdio.h>
#include <stdlib.h>

void check_counters(int size) {
    int *counters = (int*)malloc(size * sizeof(int));
    
    if (counters == NULL) return;

    if (counters[0] == 0) {
        printf("Массив готов к работе.\n");
    } else {
        printf("Обнаружены старые данные: %d\n", counters[0]);
    }

    free(counters);
};
```

### Задание 3

Опишите результат выполнения функции ниже:
```c
#include <stdio.h>
#include <stdlib.h>

void process_value(int *data) {
    *data = *data * 2; 
    printf("Новое значение: %d\n", *data);

    if (data == NULL) {
        printf("Ошибка: передан пустой указатель!\n");
        return;
    }
};
```