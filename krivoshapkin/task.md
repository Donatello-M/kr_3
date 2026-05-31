### Задание 1

Опишите разницу между

```c
free(ptr);
ptr = NULL;
```

Что именно делает функция `free(ptr)`? Зачем нужна строчка `ptr = NULL`? От какой ошибки защищает зануление указателя при повторном вызове `free(ptr)`?

### Задание 2

Опишите результат выполнения функции ниже:
```c
#include <stdlib.h>

typedef struct {
    int x;
    int y;
} Point;

int main() {
    Point *polygon = (Point*)malloc(10 * sizeof(x, y)); 
    
    if (polygon != NULL) {
        polygon[0].x = 10;
        free(polygon);
    }
    return 0;
}
```

### Задание 3

Проанализируйте работу функции:
```c
#include <stdio.h>
#include <stdlib.h>

int НайтиИПроверить(int size, int limit) {
    int *array = (int*)malloc(size * sizeof(int));
    if (array == NULL) return -1;

    if (array[0] > limit) {
        printf("Предупреждение: лимит превышен!\n");
        return 0;
    }

    free(array);
    return 1;
}
```