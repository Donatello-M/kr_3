### Задание 1

Дайте определения и сравните между собой следующие критические состояния при работе с динамической памятью:
 - Утечка памяти
 - Использование повисшего указателя

### Задание 2

Опишите результат выполнения функции ниже:
```c
#include <stdlib.h>

int* merge_buffers(int *buf1, int *buf2, int size) {
    int *result = (int*)malloc(size * 2 * sizeof(int));
    if (result == NULL) return NULL;

    for (int i = 0; i < size; i++) {
        result[i] = buf1[i];
        result[i + size] = buf2[i];
        
        free(buf1); 
        free(buf2);
    }
    
    return result;
};
```

### Задание 3

Опишите результат выполнения функции ниже:
```c
#include <stdlib.h>

int main() {
    int count = 5;
    // Выделяем память под массив double
    double *weights = (double*)malloc(count * sizeof(int)); 
    
    if (weights != NULL) {
        for (int i = 0; i < count; i++) {
            weights[i] = 999.99 * i; 
        }
        free(weights);
    }
    return 0;
};
```