# C语言上机编程题答案

## 一、基础程序设计

### 题目1答案：输入两个整数，输出它们的和、差、积、商

```c
#include <stdio.h>

int main() {
    int a, b;
    printf("请输入两个整数: ");
    scanf("%d %d", &a, &b);
    
    printf("和: %d\n", a + b);
    printf("差: %d\n", a - b);
    printf("积: %d\n", a * b);
    printf("商: %.2f\n", (float)a / b);
    
    return 0;
}
```

### 题目2答案：判断一个数是奇数还是偶数

```c
#include <stdio.h>

int main() {
    int num;
    printf("请输入一个整数: ");
    scanf("%d", &num);
    
    if (num % 2 == 0) {
        printf("%d是偶数\n", num);
    } else {
        printf("%d是奇数\n", num);
    }
    
    return 0;
}
```

### 题目3答案：求三个数中的最大值

```c
#include <stdio.h>

int main() {
    int a, b, c, max;
    printf("请输入三个整数: ");
    scanf("%d %d %d", &a, &b, &c);
    
    max = a;
    if (b > max) max = b;
    if (c > max) max = c;
    
    printf("最大值是: %d\n", max);
    
    return 0;
}
```

### 题目4答案：计算1到n的累加和

```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("请输入一个正整数: ");
    scanf("%d", &n);
    
    for (int i = 1; i <= n; i++) {
        sum += i;
    }
    
    printf("1到%d的和是: %d\n", n, sum);
    
    return 0;
}
```

### 题目5答案：输出九九乘法表

```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 9; i++) {
        for (int j = 1; j <= i; j++) {
            printf("%d*%d=%-4d", j, i, i * j);
        }
        printf("\n");
    }
    
    return 0;
}
```

## 二、数组操作

### 题目6答案：数组元素求和与平均值

```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }
    
    printf("总和: %d\n", sum);
    printf("平均值: %.2f\n", (float)sum / n);
    
    return 0;
}
```

### 题目7答案：查找数组中的最大值和最小值

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    int max = arr[0], min = arr[0];
    int max_index = 0, min_index = 0;
    
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
            max_index = i;
        }
        if (arr[i] < min) {
            min = arr[i];
            min_index = i;
        }
    }
    
    printf("最大值: %d, 下标: %d\n", max, max_index);
    printf("最小值: %d, 下标: %d\n", min, min_index);
    
    return 0;
}
```

### 题目8答案：数组逆序输出

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("逆序后: ");
    for (int i = n - 1; i >= 0; i--) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    return 0;
}
```

### 题目9答案：统计数组中某个元素出现的次数

```c
#include <stdio.h>

int main() {
    int n, x, count = 0;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("请输入要查找的数字: ");
    scanf("%d", &x);
    
    for (int i = 0; i < n; i++) {
        if (arr[i] == x) {
            count++;
        }
    }
    
    printf("%d在数组中出现了%d次\n", x, count);
    
    return 0;
}
```

### 题目10答案：删除数组中指定位置的元素

```c
#include <stdio.h>

int main() {
    int n, pos;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("请输入要删除的位置: ");
    scanf("%d", &pos);
    
    if (pos < 0 || pos >= n) {
        printf("位置无效\n");
        return 1;
    }
    
    // 将后面的元素前移
    for (int i = pos; i < n - 1; i++) {
        arr[i] = arr[i + 1];
    }
    n--;
    
    printf("删除后: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    return 0;
}
```

## 三、字符串处理

### 题目11答案：统计字符串长度（不使用strlen）

```c
#include <stdio.h>

int main() {
    char str[100];
    int len = 0;
    
    printf("请输入字符串: ");
    fgets(str, sizeof(str), stdin);
    
    while (str[len] != '\0' && str[len] != '\n') {
        len++;
    }
    
    printf("字符串长度: %d\n", len);
    
    return 0;
}
```

### 题目12答案：字符串反转

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    printf("请输入字符串: ");
    scanf("%s", str);
    
    int len = strlen(str);
    for (int i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - 1 - i];
        str[len - 1 - i] = temp;
    }
    
    printf("反转后: %s\n", str);
    
    return 0;
}
```

### 题目13答案：统计字符串中各类字符的个数

```c
#include <stdio.h>

int main() {
    char str[100];
    int letters = 0, digits = 0, spaces = 0, others = 0;
    
    printf("请输入字符串: ");
    fgets(str, sizeof(str), stdin);
    
    for (int i = 0; str[i] != '\0'; i++) {
        if ((str[i] >= 'a' && str[i] <= 'z') || (str[i] >= 'A' && str[i] <= 'Z')) {
            letters++;
        } else if (str[i] >= '0' && str[i] <= '9') {
            digits++;
        } else if (str[i] == ' ') {
            spaces++;
        } else if (str[i] != '\n') {
            others++;
        }
    }
    
    printf("字母: %d\n", letters);
    printf("数字: %d\n", digits);
    printf("空格: %d\n", spaces);
    printf("其他: %d\n", others);
    
    return 0;
}
```

### 题目14答案：字符串复制（不使用strcpy）

```c
#include <stdio.h>

int main() {
    char src[100], dest[100];
    int i = 0;
    
    printf("请输入字符串: ");
    scanf("%s", src);
    
    while (src[i] != '\0') {
        dest[i] = src[i];
        i++;
    }
    dest[i] = '\0';
    
    printf("复制后: %s\n", dest);
    
    return 0;
}
```

### 题目15答案：判断字符串是否为回文

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int is_palindrome = 1;
    
    printf("请输入字符串: ");
    scanf("%s", str);
    
    int len = strlen(str);
    for (int i = 0; i < len / 2; i++) {
        if (str[i] != str[len - 1 - i]) {
            is_palindrome = 0;
            break;
        }
    }
    
    if (is_palindrome) {
        printf("%s是回文串\n", str);
    } else {
        printf("%s不是回文串\n", str);
    }
    
    return 0;
}
```

## 四、函数应用

### 题目16答案：编写函数判断素数

```c
#include <stdio.h>

int isPrime(int n) {
    if (n <= 1) return 0;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) return 0;
    }
    return 1;
}

int main() {
    int num;
    printf("请输入一个整数: ");
    scanf("%d", &num);
    
    if (isPrime(num)) {
        printf("%d是素数\n", num);
    } else {
        printf("%d不是素数\n", num);
    }
    
    return 0;
}
```

### 题目17答案：编写函数计算阶乘

```c
#include <stdio.h>

long long factorial(int n) {
    long long result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}

int main() {
    int n;
    printf("请输入一个整数: ");
    scanf("%d", &n);
    
    printf("%d的阶乘是: %lld\n", n, factorial(n));
    
    return 0;
}
```

### 题目18答案：编写函数求两个数的最大公约数

```c
#include <stdio.h>

int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

int main() {
    int a, b;
    printf("请输入两个正整数: ");
    scanf("%d %d", &a, &b);
    
    printf("%d和%d的最大公约数是: %d\n", a, b, gcd(a, b));
    
    return 0;
}
```

### 题目19答案：编写函数实现斐波那契数列

```c
#include <stdio.h>

int fibonacci(int n) {
    if (n <= 2) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int n;
    printf("请输入项数: ");
    scanf("%d", &n);
    
    printf("斐波那契数列第%d项是: %d\n", n, fibonacci(n));
    
    return 0;
}
```

### 题目20答案：编写函数实现数组排序

```c
#include <stdio.h>

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    bubbleSort(arr, n);
    
    printf("排序后: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    return 0;
}
```

## 五、指针操作

### 题目21答案：使用指针交换两个变量的值

```c
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int a, b;
    printf("请输入两个整数: ");
    scanf("%d %d", &a, &b);
    
    printf("交换前: a=%d, b=%d\n", a, b);
    swap(&a, &b);
    printf("交换后: a=%d, b=%d\n", a, b);
    
    return 0;
}
```

### 题目22答案：使用指针遍历数组

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    int *p = arr;
    for (int i = 0; i < n; i++) {
        printf("%d ", *(p + i));
    }
    printf("\n");
    
    return 0;
}
```

### 题目23答案：使用指针实现字符串连接

```c
#include <stdio.h>

void strConcat(char *dest, char *src) {
    while (*dest != '\0') {
        dest++;
    }
    while (*src != '\0') {
        *dest = *src;
        dest++;
        src++;
    }
    *dest = '\0';
}

int main() {
    char str1[100], str2[50];
    printf("请输入第一个字符串: ");
    scanf("%s", str1);
    printf("请输入第二个字符串: ");
    scanf("%s", str2);
    
    strConcat(str1, str2);
    printf("连接后: %s\n", str1);
    
    return 0;
}
```

### 题目24答案：使用指针查找数组中的最大值

```c
#include <stdio.h>

int* findMax(int arr[], int n) {
    int *max = &arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > *max) {
            max = &arr[i];
        }
    }
    return max;
}

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    int *max = findMax(arr, n);
    printf("最大值: %d\n", *max);
    
    return 0;
}
```

### 题目25答案：动态分配数组内存

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int *arr = (int*)malloc(n * sizeof(int));
    if (arr == NULL) {
        printf("内存分配失败\n");
        return 1;
    }
    
    printf("请输入%d个整数: ", n);
    int sum = 0;
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }
    
    printf("平均值: %.2f\n", (float)sum / n);
    
    free(arr);
    return 0;
}
```

## 六、结构体应用

### 题目26答案：定义学生结构体并输入输出

```c
#include <stdio.h>

struct Student {
    char name[20];
    int id;
    float score;
};

int main() {
    struct Student stu;
    
    printf("请输入学生信息:\n");
    printf("姓名: ");
    scanf("%s", stu.name);
    printf("学号: ");
    scanf("%d", &stu.id);
    printf("成绩: ");
    scanf("%f", &stu.score);
    
    printf("\n学生信息:\n");
    printf("姓名: %s\n", stu.name);
    printf("学号: %d\n", stu.id);
    printf("成绩: %.2f\n", stu.score);
    
    return 0;
}
```

### 题目27答案：结构体数组存储多个学生信息

```c
#include <stdio.h>

struct Student {
    char name[20];
    int id;
    float score;
};

int main() {
    int n;
    printf("请输入学生人数: ");
    scanf("%d", &n);
    
    struct Student students[n];
    
    printf("请输入%d个学生的信息:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%s %d %f", students[i].name, &students[i].id, &students[i].score);
    }
    
    printf("\n所有学生信息:\n");
    for (int i = 0; i < n; i++) {
        printf("学生%d: %s, 学号: %d, 成绩: %.2f\n", 
               i + 1, students[i].name, students[i].id, students[i].score);
    }
    
    return 0;
}
```

### 题目28答案：查找成绩最高的学生

```c
#include <stdio.h>

struct Student {
    char name[20];
    int id;
    float score;
};

int main() {
    int n;
    printf("请输入学生人数: ");
    scanf("%d", &n);
    
    struct Student students[n];
    
    printf("请输入%d个学生的信息:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%s %d %f", students[i].name, &students[i].id, &students[i].score);
    }
    
    int max_index = 0;
    for (int i = 1; i < n; i++) {
        if (students[i].score > students[max_index].score) {
            max_index = i;
        }
    }
    
    printf("成绩最高的学生: %s, 学号: %d, 成绩: %.2f\n", 
           students[max_index].name, students[max_index].id, students[max_index].score);
    
    return 0;
}
```

### 题目29答案：按成绩对学生排序

```c
#include <stdio.h>

struct Student {
    char name[20];
    int id;
    float score;
};

int main() {
    int n;
    printf("请输入学生人数: ");
    scanf("%d", &n);
    
    struct Student students[n];
    
    printf("请输入%d个学生的信息:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%s %d %f", students[i].name, &students[i].id, &students[i].score);
    }
    
    // 冒泡排序（按成绩降序）
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - 1 - i; j++) {
            if (students[j].score < students[j + 1].score) {
                struct Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }
    
    printf("\n排序后:\n");
    for (int i = 0; i < n; i++) {
        printf("%s %d %.2f\n", students[i].name, students[i].id, students[i].score);
    }
    
    return 0;
}
```

### 题目30答案：使用结构体指针访问成员

```c
#include <stdio.h>

struct Student {
    char name[20];
    int id;
    float score;
};

int main() {
    struct Student stu;
    struct Student *p = &stu;
    
    printf("请输入学生信息:\n");
    scanf("%s %d %f", p->name, &p->id, &p->score);
    
    printf("修改前: %s, 学号: %d, 成绩: %.2f\n", p->name, p->id, p->score);
    
    printf("请输入新成绩: ");
    scanf("%f", &p->score);
    
    printf("修改后: %s, 学号: %d, 成绩: %.2f\n", p->name, p->id, p->score);
    
    return 0;
}
```

## 七、排序算法

### 题目31答案：冒泡排序

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    // 冒泡排序
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
    
    printf("排序后: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    return 0;
}
```

### 题目32答案：选择排序

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    // 选择排序
    for (int i = 0; i < n - 1; i++) {
        int min_index = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[min_index]) {
                min_index = j;
            }
        }
        if (min_index != i) {
            int temp = arr[i];
            arr[i] = arr[min_index];
            arr[min_index] = temp;
        }
    }
    
    printf("排序后: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    return 0;
}
```

### 题目33答案：插入排序

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    // 插入排序
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
    
    printf("排序后: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    return 0;
}
```

## 八、查找算法

### 题目34答案：顺序查找

```c
#include <stdio.h>

int main() {
    int n, x;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("请输入要查找的数字: ");
    scanf("%d", &x);
    
    int pos = -1;
    for (int i = 0; i < n; i++) {
        if (arr[i] == x) {
            pos = i;
            break;
        }
    }
    
    if (pos != -1) {
        printf("%d在数组中的位置是: %d\n", x, pos);
    } else {
        printf("%d不在数组中\n", x);
    }
    
    return 0;
}
```

### 题目35答案：二分查找

```c
#include <stdio.h>

int binarySearch(int arr[], int n, int x) {
    int left = 0, right = n - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == x) {
            return mid;
        } else if (arr[mid] < x) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return -1;
}

int main() {
    int n, x;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个有序整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("请输入要查找的数字: ");
    scanf("%d", &x);
    
    int pos = binarySearch(arr, n, x);
    
    if (pos != -1) {
        printf("%d在数组中的位置是: %d\n", x, pos);
    } else {
        printf("%d不在数组中\n", x);
    }
    
    return 0;
}
```

## 九、递归算法

### 题目36答案：递归计算n的阶乘

```c
#include <stdio.h>

long long factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

int main() {
    int n;
    printf("请输入一个整数: ");
    scanf("%d", &n);
    
    printf("%d的阶乘是: %lld\n", n, factorial(n));
    
    return 0;
}
```

### 题目37答案：递归求斐波那契数列

```c
#include <stdio.h>

int fibonacci(int n) {
    if (n <= 2) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int n;
    printf("请输入项数: ");
    scanf("%d", &n);
    
    printf("斐波那契数列第%d项是: %d\n", n, fibonacci(n));
    
    return 0;
}
```

### 题目38答案：递归实现数组求和

```c
#include <stdio.h>

int arraySum(int arr[], int n) {
    if (n == 0) return 0;
    return arr[n - 1] + arraySum(arr, n - 1);
}

int main() {
    int n;
    printf("请输入元素个数: ");
    scanf("%d", &n);
    
    int arr[n];
    printf("请输入%d个整数: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("数组元素之和: %d\n", arraySum(arr, n));
    
    return 0;
}
```

### 题目39答案：递归求最大公约数

```c
#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0) return a;
    return gcd(b, a % b);
}

int main() {
    int a, b;
    printf("请输入两个正整数: ");
    scanf("%d %d", &a, &b);
    
    printf("%d和%d的最大公约数是: %d\n", a, b, gcd(a, b));
    
    return 0;
}
```

### 题目40答案：递归实现字符串反转

```c
#include <stdio.h>
#include <string.h>

void reverseString(char str[], int start, int end) {
    if (start >= end) return;
    char temp = str[start];
    str[start] = str[end];
    str[end] = temp;
    reverseString(str, start + 1, end - 1);
}

int main() {
    char str[100];
    printf("请输入字符串: ");
    scanf("%s", str);
    
    int len = strlen(str);
    reverseString(str, 0, len - 1);
    
    printf("反转后: %s\n", str);
    
    return 0;
}
```

## 十、综合应用

### 题目41答案：杨辉三角

```c
#include <stdio.h>

int main() {
    int n;
    printf("请输入行数: ");
    scanf("%d", &n);
    
    int triangle[n][n];
    
    for (int i = 0; i < n; i++) {
        for (int j = 0; j <= i; j++) {
            if (j == 0 || j == i) {
                triangle[i][j] = 1;
            } else {
                triangle[i][j] = triangle[i-1][j-1] + triangle[i-1][j];
            }
            printf("%d ", triangle[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

### 题目42答案：矩阵转置

```c
#include <stdio.h>

int main() {
    int m, n;
    printf("请输入矩阵的行数和列数: ");
    scanf("%d %d", &m, &n);
    
    int matrix[m][n], transpose[n][m];
    
    printf("请输入矩阵元素:\n");
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    
    // 转置
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            transpose[j][i] = matrix[i][j];
        }
    }
    
    printf("转置后:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            printf("%d ", transpose[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

### 题目43答案：统计单词个数

```c
#include <stdio.h>

int main() {
    char str[200];
    int count = 0, in_word = 0;
    
    printf("请输入句子: ");
    fgets(str, sizeof(str), stdin);
    
    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] == ' ' || str[i] == '\n' || str[i] == '\t') {
            in_word = 0;
        } else if (in_word == 0) {
            in_word = 1;
            count++;
        }
    }
    
    printf("单词个数: %d\n", count);
    
    return 0;
}
```

### 题目44答案：进制转换（十进制转二进制）

```c
#include <stdio.h>

void decimalToBinary(int n) {
    if (n == 0) return;
    decimalToBinary(n / 2);
    printf("%d", n % 2);
}

int main() {
    int num;
    printf("请输入十进制数: ");
    scanf("%d", &num);
    
    printf("%d的二进制是: ", num);
    if (num == 0) {
        printf("0");
    } else {
        decimalToBinary(num);
    }
    printf("\n");
    
    return 0;
}
```

### 题目45答案：完数判断

```c
#include <stdio.h>

int main() {
    int num, sum = 0;
    printf("请输入一个正整数: ");
    scanf("%d", &num);
    
    for (int i = 1; i < num; i++) {
        if (num % i == 0) {
            sum += i;
        }
    }
    
    if (sum == num) {
        printf("%d是完数\n", num);
    } else {
        printf("%d不是完数\n", num);
    }
    
    return 0;
}
```

### 题目46答案：水仙花数

```c
#include <stdio.h>

int main() {
    printf("三位水仙花数有:\n");
    
    for (int i = 100; i < 1000; i++) {
        int a = i / 100;
        int b = (i / 10) % 10;
        int c = i % 10;
        
        if (i == a*a*a + b*b*b + c*c*c) {
            printf("%d\n", i);
        }
    }
    
    return 0;
}
```

### 题目47答案：简单计算器

```c
#include <stdio.h>

int main() {
    float num1, num2, result;
    char op;
    
    printf("请输入表达式 (如: 10 + 5): ");
    scanf("%f %c %f", &num1, &op, &num2);
    
    switch(op) {
        case '+':
            result = num1 + num2;
            break;
        case '-':
            result = num1 - num2;
            break;
        case '*':
            result = num1 * num2;
            break;
        case '/':
            if (num2 != 0) {
                result = num1 / num2;
            } else {
                printf("错误: 除数不能为0\n");
                return 1;
            }
            break;
        default:
            printf("错误: 无效的运算符\n");
            return 1;
    }
    
    printf("结果: %.2f\n", result);
    
    return 0;
}
```

### 题目48答案：成绩等级判定

```c
#include <stdio.h>

int main() {
    float score;
    printf("请输入成绩: ");
    scanf("%f", &score);
    
    if (score >= 90 && score <= 100) {
        printf("等级: A\n");
    } else if (score >= 80) {
        printf("等级: B\n");
    } else if (score >= 70) {
        printf("等级: C\n");
    } else if (score >= 60) {
        printf("等级: D\n");
    } else if (score >= 0) {
        printf("等级: E\n");
    } else {
        printf("无效的成绩\n");
    }
    
    return 0;
}
```

### 题目49答案：猜数字游戏

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(NULL));
    int target = rand() % 100 + 1;
    int guess;
    
    printf("我想了一个1-100之间的数字，请猜猜是多少\n");
    
    while (1) {
        printf("猜一个1-100之间的数字: ");
        scanf("%d", &guess);
        
        if (guess < target) {
            printf("太小了\n");
        } else if (guess > target) {
            printf("太大了\n");
        } else {
            printf("恭喜你猜对了！\n");
            break;
        }
    }
    
    return 0;
}
```

### 题目50答案：通讯录管理系统（综合项目）

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_CONTACTS 100

struct Contact {
    char name[50];
    char phone[20];
    char email[50];
};

struct Contact contacts[MAX_CONTACTS];
int count = 0;

void addContact() {
    if (count >= MAX_CONTACTS) {
        printf("通讯录已满！\n");
        return;
    }
    
    printf("请输入姓名: ");
    scanf("%s", contacts[count].name);
    printf("请输入电话: ");
    scanf("%s", contacts[count].phone);
    printf("请输入邮箱: ");
    scanf("%s", contacts[count].email);
    
    count++;
    printf("添加成功！\n");
}

void viewContacts() {
    if (count == 0) {
        printf("通讯录为空！\n");
        return;
    }
    
    printf("\n所有联系人:\n");
    printf("%-20s %-15s %-30s\n", "姓名", "电话", "邮箱");
    printf("---------------------------------------------------------------\n");
    for (int i = 0; i < count; i++) {
        printf("%-20s %-15s %-30s\n", 
               contacts[i].name, contacts[i].phone, contacts[i].email);
    }
}

void searchContact() {
    char keyword[50];
    printf("请输入要查找的姓名: ");
    scanf("%s", keyword);
    
    int found = 0;
    for (int i = 0; i < count; i++) {
        if (strstr(contacts[i].name, keyword) != NULL) {
            printf("姓名: %s, 电话: %s, 邮箱: %s\n", 
                   contacts[i].name, contacts[i].phone, contacts[i].email);
            found = 1;
        }
    }
    
    if (!found) {
        printf("未找到匹配的联系人！\n");
    }
}

void deleteContact() {
    char name[50];
    printf("请输入要删除的联系人姓名: ");
    scanf("%s", name);
    
    int index = -1;
    for (int i = 0; i < count; i++) {
        if (strcmp(contacts[i].name, name) == 0) {
            index = i;
            break;
        }
    }
    
    if (index == -1) {
        printf("未找到该联系人！\n");
        return;
    }
    
    for (int i = index; i < count - 1; i++) {
        contacts[i] = contacts[i + 1];
    }
    count--;
    printf("删除成功！\n");
}

void saveToFile() {
    FILE *fp = fopen("contacts.dat", "wb");
    if (fp == NULL) {
        printf("无法保存文件！\n");
        return;
    }
    
    fwrite(&count, sizeof(int), 1, fp);
    fwrite(contacts, sizeof(struct Contact), count, fp);
    fclose(fp);
    printf("保存成功！\n");
}

void loadFromFile() {
    FILE *fp = fopen("contacts.dat", "rb");
    if (fp == NULL) {
        return;
    }
    
    fread(&count, sizeof(int), 1, fp);
    fread(contacts, sizeof(struct Contact), count, fp);
    fclose(fp);
}

int main() {
    loadFromFile();
    
    int choice;
    while (1) {
        printf("\n========== 通讯录管理系统 ==========\n");
        printf("1. 添加联系人\n");
        printf("2. 查看所有联系人\n");
        printf("3. 搜索联系人\n");
        printf("4. 删除联系人\n");
        printf("5. 保存并退出\n");
        printf("====================================\n");
        printf("请输入您的选择: ");
        scanf("%d", &choice);
        
        switch(choice) {
            case 1:
                addContact();
                break;
            case 2:
                viewContacts();
                break;
            case 3:
                searchContact();
                break;
            case 4:
                deleteContact();
                break;
            case 5:
                saveToFile();
                printf("再见！\n");
                return 0;
            default:
                printf("无效的选择！\n");
        }
    }
    
    return 0;
}
```
