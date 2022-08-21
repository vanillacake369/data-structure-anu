# Report : Sorting Algorithms

Ji-Hoon Lim

Dept of Computer Engineering, Andong National University

e-mail : 1026baby@naver.com

# Contents

# Abstract

컴퓨터 분야에서 사용하는 데이터의 경우 어휘 또는 숫자의 순서를 기반으로 정렬한 후 사용해야 하는 경우가 빈번하게 발생한다. 경우에 따라 얼마나 효과적으로 정렬을 실시하느냐는 컴퓨터 분야에서 중요시 되는 문제이다. 본 보고서는 정렬을 사용해야하는 이유와 특징들을 나열한 뒤, 대표적인 정렬 알고리즘의 구현과정과 각 경우에 따른 효과적인 정렬 알고리즘은 무엇인지를 기술한다.

# Introduction

## Why use Sorting Algorithms?

정렬은 컴퓨터 과학에서 굉장히 기초적인 알고리즘 중 하나로서, 데이터베이스에서 가장 흔히 사용되는 명령으로 질의 결과를 순서에 따라 나열하거나 조인, 인덱싱의 일부분으로서 역할을 수행한다.[[1]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

입력된 데이터들을 정렬된 리스트의 형태로 요구하는 탐색 알고리즘과 병합 알고리즘과 같이, 다른 알고리즘의 효율성을 최적화하기 위해서는, 효율적인 정렬은 굉장히 중요하다. 정렬은 데이터 정규화와 사람에 친화적인 데이터를 생산해내는 데에 주로 쓰인다. [[2]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

## Condition of Sorting Algorithms

형식적으로 정렬 알고리즘의 출력은 다음 두 조건을 만족해야 한다.

1. 출력은 단조로운 순서의 형태이여한다. 즉, 요구된 순서를 보존하거나 뒤집는 순서집합의 형태이여야 한다.
2. 출력은 입력에 대한 순열의 형태이여야한다.  즉, 선형순서의 형태로 데이터들이 재구성 혹은 배치되어있는 형태이여한다. [[3]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md) 

## Classification on Sorting ALG [](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

- 계산복잡성
    - 리스트의 크기에 있어 최상의 경우, 최악의 경우 및 평균적인 경우가 있다. 일반적인 직렬 정렬 알고리즘의 경우, 최상의 행동(good behavior)은 O(n logn), 병렬 정렬은 O(logn), 최악의 행동(bad behavior)은 O(n)이다. 직렬 정렬의 이상적인 동작은 O(n)이지만, 평균적으로 이는 불가능하다. 최적의 병렬 정렬은 O(log n)이다. [[4]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)
- 메모리 사용량 (및 다른 컴퓨터 리소스 사용)
    - 정렬 중인 벡터 혹은 리스트에 n개의 요소가 있는 경우, 힙소트와 같은 제자리 정렬 알고리즘은 n개의 요소를 저장하는 데 필요한 추가 메모리가 필요하지 않다. 엄밀하게 말하면, 제자리 정렬은 정렬할 항목을 제외한 O(1) 메모리만 필요로 한다. 때때로 O(log n) 추가 메모리는 제자리정렬로 간주된다.
    - 그러나 많은 다른 알고리즘들은 내부 알고리즘보다 더 많은 메모리를 필요로 한다. 예를 들어, 벡터 자체만큼 더 많은 메모리를 필요로 하는 것들은 n의 메모리 요구 사항을 가지고 있다고 한다. 알고리즘의 메모리 사용량을 사전에 인지하는 것은 굉장히 중요하다. 정렬 알고리즘은, 특히 대규모 데이터 세트를 정렬하는 경우, 작은 IoT 장치에서 실행할 수 있는 충분한 메모리가 없을 수 있기 때문이다.
- 재귀호출
    - 어떤 정렬 알고리즘은 재귀적이거나 비재귀적인 알고리즘이거나 혹은 둘 다 일 수 있다. (병합 정렬을 예로 들 수 있다)
- 안정성
    - 안정적인 정렬 알고리즘은 동일한 키(즉, 값)에 대해 레코드의 상대적 순서를 유지한다.
- 비교 정렬
    - 비교 정렬은 두 요소를 비교하기 위한 비교 연산자를 통해서만 데이터를 검사한다.
- 적응성
    - 입력에 대해 사전에 실행한 정렬이 실행 시간에 영향을 미치는지 여부를 뜻한다. 이를 고려한 정렬 알고리즘을 적응적인 정렬 알고리즘이라고 한다.

# Typical Sorting Algorithms

정렬 알고리즘은 현재 컴퓨터과학에서 가장 깊게, 그리고 활발히 연구된 분야 중 하나이다. 현재 연구된 정렬 알고리즘의 종류는 셀 수 없을 정도로 많이 있지만, 대표적으로 쓰이는 정렬 알고리즘은 다음과 같다. 

- Bubble Sort
- Selection Sort
- Insertion Sort
- Merge Sort
- Quicksort
- Counting Sort
- Radix Sort
- Bucket Sort
- Heap Sort
- Shell Sort

# Bubble Sort

## About Bubble Sort

버블정렬(bubble sort)은 서로 인접한 2개의 레코드를 비교한 후 정렬 기준에 맞지 않는다면 서로 교환하는 비교&교환 과정을 리스트의 한쪽 끝에서 시작하여 다른 쪽 끝까지 진행한다. 이러한 리스트의 비교&교환 과정을 한번 실행하면 가장 큰 값을 가진 레코드가 리스트의 가장 끝으로 이동된다. 이러한 비교&교환 과정을 전체 리스트가 기준에 부합하게 정렬될 때까지 반복한다.

## C Code of Bubble Sort

```c
#include <stdio.h>

int main(){
    int arr[50], num, x, y, temp;    
    printf("Please Enter the Number of Elements you want in the array: ");
    scanf("%d", &num);    
    printf("Please Enter the Value of Elements: ");
    for(x = 0; x < num; x++)
        scanf("%d", &arr[x]);
    for(x = 0; x < num - 1; x++){       
        for(y = 0; y < num - x - 1; y++){          
            if(arr[y] > arr[y + 1]){               
                temp = arr[y];
                arr[y] = arr[y + 1];
                arr[y + 1] = temp;
            }
        }
    }
    printf("Array after implementing bubble sort: ");
    for(x = 0; x < num; x++){
        printf("%d  ", arr[x]);
    }
    return 0;
}
```

# Selection Sort

## About Selection Sort

선택정렬(selection sort)은 학습을 하는데 있어 먼저 두 개의 리스트가 있다고 가정한다. 하나의 리스트에는 정렬이 완료된 숫자들을 저장하고 또 다른 리스트에는 정렬되지 않은 숫자들이 저장되어 있다. 선택정렬은 정렬되지 않은 숫자들이 저장되어 있는 리스트에서 가장 작은 숫자를 선택하여 또 다른 리스트로 이동하는 작업을 되풀이 한다. 숫자가 저장되어 있는 리스트가 공백이 될 때까지 이 과정을 되풀이하는 정렬 기법이 선택정렬 기법이다. 

## C Code of Selection Sort

```c
// C program for implementation of selection sort
#include <stdio.h>
  
void swap(int *xp, int *yp)
{
    int temp = *xp;
    *xp = *yp;
    *yp = temp;
}
void selectionSort(int arr[], int n)
{
    int i, j, min_idx;
    // One by one move boundary of unsorted subarray
    for (i = 0; i < n-1; i++)
    {
        // Find the minimum element in unsorted array
        min_idx = i;
        for (j = i+1; j < n; j++)
          if (arr[j] < arr[min_idx])
            min_idx = j;
        // Swap the found minimum element with the first element
        swap(&arr[min_idx], &arr[i]);
    }
}
  
/* Function to print an array */
void printArray(int arr[], int size)
{
    int i;
    for (i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}
  
// Driver program to test above functions
int main()
{
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr)/sizeof(arr[0]);
    selectionSort(arr, n);
    printf("Sorted array: \n");
    printArray(arr, n);
    return 0;
}
```

# Insertion Sort

## About Insertion Sort

삽입정렬(insertion sort)은 도서관의 도서 시리즈를 재배치하는 과정과 비슷하다. 선택정렬과 마찬가지로 두 개의 리스트가 있다고 가정한다. 삽입정렬이 실행되기 전 리스트의 첫 번째 숫자가 삽입정렬이 실행된 후 리스트에서 어떤 위치에 삽입되어야 하는지를 판단, 판단 후 해당하는 위치에 이 숫자를 삽입하게 되면, 삽입정렬이 실행 된 후 리스트의 크기는 하나 커지게 되고, 삽입정렬이 실행되기 전 리스트의 크기는 삽입정렬이 실행된 만큼 줄어들게 된다. 이러한 과정을 정렬되지 않은 부분이 빌 때까지 반복한다. 

## C Code of Insertion Sort

```c
// C program for insertion sort
#include <math.h>
#include <stdio.h>
 
/* Function to sort an array using insertion sort*/
void insertionSort(int arr[], int n)
{
    int i, key, j;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
 
        /* Move elements of arr[0..i-1], that are
          greater than key, to one position ahead
          of their current position */
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}
 
// A utility function to print an array of size n
void printArray(int arr[], int n)
{
    int i;
    for (i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
}
 
/* Driver program to test insertion sort */
int main()
{
    int arr[] = { 12, 11, 13, 5, 6 };
    int n = sizeof(arr) / sizeof(arr[0]);
 
    insertionSort(arr, n);
    printArray(arr, n);
 
    return 0;
}
```

# Merge Sort

## About Merge Sort

합병정렬(merge sort)은 분할 정복(divide and conquer) 기법에 바탕을 두고 있다. 합병정렬은 하나의 리스트를 두 개의 균등한 크기를 가진 리스트로 분할하고 분할된 부분 리스트를 더 이상 분할되지 않을 때까지 분할한다. 더 이상 분할되지 않는 부분 리스트부터 정렬한 후 다시 정렬된 부분 리스트들을 합하는 과정을 반복해 전체가 정렬된 리스트를 얻는 것이다. 

## C Code of Merge Sort

```c
/* C program for Merge Sort */
#include <stdio.h>
#include <stdlib.h>
  
// Merges two subarrays of arr[].
// First subarray is arr[l..m]
// Second subarray is arr[m+1..r]
void merge(int arr[], int l, int m, int r)
{
    int i, j, k;
    int n1 = m - l + 1;
    int n2 = r - m;
  
    /* create temp arrays */
    int L[n1], R[n2];
  
    /* Copy data to temp arrays L[] and R[] */
    for (i = 0; i < n1; i++)
        L[i] = arr[l + i];
    for (j = 0; j < n2; j++)
        R[j] = arr[m + 1 + j];
  
    /* Merge the temp arrays back into arr[l..r]*/
    i = 0; // Initial index of first subarray
    j = 0; // Initial index of second subarray
    k = l; // Initial index of merged subarray
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        }
        else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }
  
    /* Copy the remaining elements of L[], if there
    are any */
    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }
  
    /* Copy the remaining elements of R[], if there
    are any */
    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}
  
/* l is for left index and r is right index of the
sub-array of arr to be sorted */
void mergeSort(int arr[], int l, int r)
{
    if (l < r) {
        // Same as (l+r)/2, but avoids overflow for
        // large l and h
        int m = l + (r - l) / 2;
  
        // Sort first and second halves
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
  
        merge(arr, l, m, r);
    }
}
  
/* UTILITY FUNCTIONS */
/* Function to print an array */
void printArray(int A[], int size)
{
    int i;
    for (i = 0; i < size; i++)
        printf("%d ", A[i]);
    printf("\n");
}
  
/* Driver code */
int main()
{
    int arr[] = { 12, 11, 13, 5, 6, 7 };
    int arr_size = sizeof(arr) / sizeof(arr[0]);
  
    printf("Given array is \n");
    printArray(arr, arr_size);
  
    mergeSort(arr, 0, arr_size - 1);
  
    printf("\nSorted array is \n");
    printArray(arr, arr_size);
    return 0;
}
```

# Quicksort

## About Quick Sort

퀵 정렬(quick sort) 또한 합병정렬과 마찬가지로 분할 정복 기법에 바탕을 두고 있다. 퀵 정렬은 전체 리스트를 2개의 부분 리스트로 분할하고, 각각의 리스트에 퀵 정렬을 실행하는 분할 정복 기법을 사용한다. 합병정렬과의 차이를 리스트를 비 균등하게 분할한다는 것이다. 리스트의 한 데이터를 피벗(pivot)이라는 키로 선택하고 이러한 피벗 키를 기준으로 좌우에 데이터를 정렬한다. 

## C Code of Quick Sort

```c
// Quick sort in C

#include <stdio.h>

// function to swap elements
void swap(int *a, int *b) {
  int t = *a;
  *a = *b;
  *b = t;
}

// function to find the partition position
int partition(int array[], int low, int high) {
  
  // select the rightmost element as pivot
  int pivot = array[high];
  
  // pointer for greater element
  int i = (low - 1);

  // traverse each element of the array
  // compare them with the pivot
  for (int j = low; j < high; j++) {
    if (array[j] <= pivot) {
        
      // if element smaller than pivot is found
      // swap it with the greater element pointed by i
      i++;
      
      // swap element at i with element at j
      swap(&array[i], &array[j]);
    }
  }

  // swap the pivot element with the greater element at i
  swap(&array[i + 1], &array[high]);
  
  // return the partition point
  return (i + 1);
}

void quickSort(int array[], int low, int high) {
  if (low < high) {
    
    // find the pivot element such that
    // elements smaller than pivot are on left of pivot
    // elements greater than pivot are on right of pivot
    int pi = partition(array, low, high);
    
    // recursive call on the left of pivot
    quickSort(array, low, pi - 1);
    
    // recursive call on the right of pivot
    quickSort(array, pi + 1, high);
  }
}

// function to print array elements
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

// main function
int main() {
  int data[] = {8, 7, 2, 1, 0, 9, 6};
  
  int n = sizeof(data) / sizeof(data[0]);
  
  printf("Unsorted Array\n");
  printArray(data, n);
  
  // perform quicksort on data
  quickSort(data, 0, n - 1);
  
  printf("Sorted array in ascending order: \n");
  printArray(data, n);
}
```

# Counting Sort

## About Counting Sort

계수정렬(Counting Sort)는 요소 값들끼리 서로 비교하지 않고 정렬하는 Non-Comparison Sort 기법 중 하나로서, 원소값들의 개수를 저장하는 누적합 배열(Counting Array)을 생성한다. 누적합 배열의 요소들에 대하여 직전 요소들의 값을 더해준 뒤, 입력 배열과 동일크기의 출력 배열을 생성하여 입력 배열의 역순으로 요소들을 채워넣어준다. 이를 통해 원소 간 비교 없이 정렬이 수행될 수 있다. 

## C Code of Counting Sort

```c
// Counting sort in C programming

#include <stdio.h>

void countingSort(int array[], int size) {
  int output[10];

  // Find the largest element of the array
  int max = array[0];
  for (int i = 1; i < size; i++) {
    if (array[i] > max)
      max = array[i];
  }

  // The size of count must be at least (max+1) but
  // we cannot declare it as int count(max+1) in C as
  // it does not support dynamic memory allocation.
  // So, its size is provided statically.
  int count[10];

  // Initialize count array with all zeros.
  for (int i = 0; i <= max; ++i) {
    count[i] = 0;
  }

  // Store the count of each element
  for (int i = 0; i < size; i++) {
    count[array[i]]++;
  }

  // Store the cummulative count of each array
  for (int i = 1; i <= max; i++) {
    count[i] += count[i - 1];
  }

  // Find the index of each element of the original array in count array, and
  // place the elements in output array
  for (int i = size - 1; i >= 0; i--) {
    output[count[array[i]] - 1] = array[i];
    count[array[i]]--;
  }

  // Copy the sorted elements into original array
  for (int i = 0; i < size; i++) {
    array[i] = output[i];
  }
}

// Function to print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

// Driver code
int main() {
  int array[] = {4, 2, 2, 8, 3, 3, 1};
  int n = sizeof(array) / sizeof(array[0]);
  countingSort(array, n);
  printArray(array, n);
}
```

# Radix Sort

## About Radix Sort

기수 정렬(Radix Sort)는 다른 정렬 알고리즘과 달리, 각 원소 간의 비교가 아닌 낮은 자리수부터 비교하여 정렬해 간다는 것을 기본 개념으로 하며,  비교 연산을 하지 않고 정렬 속도가 빠르지만 데이터 전체 크기에 기수 테이블의 크기만한 메모리가 더 필요한 정렬 알고리즘이다. 데이터 중 가장 큰 자릿수를 구한 뒤, 가장 작은 자릿수부터, 가장 큰 자릿수까지 해당 자릿수만을 보고 계수정렬을 진행한다. 가장 작은 자리수부터 비교하는 방법을 LSD(Least-Significant-Digit)라고 하며 가장 큰 자리수부터 비교하는 방법은 MSD(Most-Significant-Digit)라고 부른다.

## C Code of Radix Sort

```c
// Radix Sort in C Programming

#include <stdio.h>

// Function to get the largest element from an array
int getMax(int array[], int n) {
  int max = array[0];
  for (int i = 1; i < n; i++)
    if (array[i] > max)
      max = array[i];
  return max;
}

// Using counting sort to sort the elements in the basis of significant places
void countingSort(int array[], int size, int place) {
  int output[size + 1];
  int max = (array[0] / place) % 10;

  for (int i = 1; i < size; i++) {
    if (((array[i] / place) % 10) > max)
      max = array[i];
  }
  int count[max + 1];

  for (int i = 0; i < max; ++i)
    count[i] = 0;

  // Calculate count of elements
  for (int i = 0; i < size; i++)
    count[(array[i] / place) % 10]++;
    
  // Calculate cumulative count
  for (int i = 1; i < 10; i++)
    count[i] += count[i - 1];

  // Place the elements in sorted order
  for (int i = size - 1; i >= 0; i--) {
    output[count[(array[i] / place) % 10] - 1] = array[i];
    count[(array[i] / place) % 10]--;
  }

  for (int i = 0; i < size; i++)
    array[i] = output[i];
}

// Main function to implement radix sort
void radixsort(int array[], int size) {
  // Get maximum element
  int max = getMax(array, size);

  // Apply counting sort to sort elements based on place value.
  for (int place = 1; max / place > 0; place *= 10)
    countingSort(array, size, place);
}

// Print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

// Driver code
int main() {
  int array[] = {121, 432, 564, 23, 1, 45, 788};
  int n = sizeof(array) / sizeof(array[0]);
  radixsort(array, n);
  printArray(array, n);
}
```

# Bucket Sort

## About Bucket Sort

버킷 정렬이란 배열의 원소를 여러 버킷으로 분산하여 작동하는 정렬 알고리즘이다. 버킷은 빈(bin)이라고도 불리고, 버킷 정렬도 빈 정렬로도 불린다. 각 버킷은 다른 정렬 알고리즘을 사용하거나 버킷 정렬을 반복 적용해 각각 정렬한다. 먼저 빈 버킷의 배열을 준비한 뒤, 정렬할 배열의 원소를 각각 버킷에 넣는다. 이후, 내용물이 있는 각 버킷을 정렬한 뒤, 버킷을 순서대로 방문하여 모든 원소를 원래 배열에 다시 넣는다. 이 때, 버킷 속에서의 정렬에 대하여  어떤 정렬을 사용하는지에 따라 시간복잡도가 상이하다. 아래 코드는 삽입 정렬을 사용하였다. [[6]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

## C Code of Bucket Sort

```c
// Bucket sort in C

#include <stdio.h>
#include <stdlib.h>

#define NARRAY 7   // Array size
#define NBUCKET 6  // Number of buckets
#define INTERVAL 10  // Each bucket capacity

struct Node {
  int data;
  struct Node *next;
};

void BucketSort(int arr[]);
struct Node *InsertionSort(struct Node *list);
void print(int arr[]);
void printBuckets(struct Node *list);
int getBucketIndex(int value);

// Sorting function
void BucketSort(int arr[]) {
  int i, j;
  struct Node **buckets;

  // Create buckets and allocate memory size
  buckets = (struct Node **)malloc(sizeof(struct Node *) * NBUCKET);

  // Initialize empty buckets
  for (i = 0; i < NBUCKET; ++i) {
    buckets[i] = NULL;
  }

  // Fill the buckets with respective elements
  for (i = 0; i < NARRAY; ++i) {
    struct Node *current;
    int pos = getBucketIndex(arr[i]);
    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = arr[i];
    current->next = buckets[pos];
    buckets[pos] = current;
  }

  // Print the buckets along with their elements
  for (i = 0; i < NBUCKET; i++) {
    printf("Bucket[%d]: ", i);
    printBuckets(buckets[i]);
    printf("\n");
  }

  // Sort the elements of each bucket
  for (i = 0; i < NBUCKET; ++i) {
    buckets[i] = InsertionSort(buckets[i]);
  }

  printf("-------------\n");
  printf("Bucktets after sorting\n");
  for (i = 0; i < NBUCKET; i++) {
    printf("Bucket[%d]: ", i);
    printBuckets(buckets[i]);
    printf("\n");
  }

  // Put sorted elements on arr
  for (j = 0, i = 0; i < NBUCKET; ++i) {
    struct Node *node;
    node = buckets[i];
    while (node) {
      arr[j++] = node->data;
      node = node->next;
    }
  }

  return;
}

// Function to sort the elements of each bucket
struct Node *InsertionSort(struct Node *list) {
  struct Node *k, *nodeList;
  if (list == 0 || list->next == 0) {
    return list;
  }

  nodeList = list;
  k = list->next;
  nodeList->next = 0;
  while (k != 0) {
    struct Node *ptr;
    if (nodeList->data > k->data) {
      struct Node *tmp;
      tmp = k;
      k = k->next;
      tmp->next = nodeList;
      nodeList = tmp;
      continue;
    }

    for (ptr = nodeList; ptr->next != 0; ptr = ptr->next) {
      if (ptr->next->data > k->data)
        break;
    }

    if (ptr->next != 0) {
      struct Node *tmp;
      tmp = k;
      k = k->next;
      tmp->next = ptr->next;
      ptr->next = tmp;
      continue;
    } else {
      ptr->next = k;
      k = k->next;
      ptr->next->next = 0;
      continue;
    }
  }
  return nodeList;
}

int getBucketIndex(int value) {
  return value / INTERVAL;
}

void print(int ar[]) {
  int i;
  for (i = 0; i < NARRAY; ++i) {
    printf("%d ", ar[i]);
  }
  printf("\n");
}

// Print buckets
void printBuckets(struct Node *list) {
  struct Node *cur = list;
  while (cur) {
    printf("%d ", cur->data);
    cur = cur->next;
  }
}

// Driver code
int main(void) {
  int array[NARRAY] = {42, 32, 33, 52, 37, 47, 51};

  printf("Initial array: ");
  print(array);
  printf("-------------\n");

  BucketSort(array);
  printf("-------------\n");
  printf("Sorted array: ");
  print(array);
  return 0;
}
```

# Heap Sort

## About Heap Sort

힙 정렬을 알기 위해서는 힙 구조와 최대 힙,최소 힙트리에 대해서 알아야한다. 힙 구조는 1964년도에 J.W.J. 윌리엄스에 의해 발명된 구조로 우선순위 큐를 위하여 만들어진 자료구조로서, 최댓값 혹은 최솟값을 쉽게 추출할 수 있는 구조이다. 최대 힙 트리란 부모 노드의 키 값이 자식 노드의 키값보다 항상 크거나 같은 크기의 관계, 즉 (부모 노드의 키값 ≥ 자식 노드의 키값}의 관계를 가지는 노드들의 완전 이진트리이다. 힙 정렬은 최대 힙 트리 혹은 최소 힙 트리를 구성한 뒤, 해당 자료구조에 대한 삽입,삭제를 통하여 정렬하는 형식이다. [[7]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

## Insertion of Max Heap

![Untitled](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c/Untitled.png)

1. 힙 크기를 하나 증가시켜서 노드위치를 확장한다.
2. 확장한 노드 번호가 임시 삽입 위치 i가 된다.
3. 삽입할 원소 item과 부모 노드 heap[i/2]를 비교하여 부모 노드보다 작거나 같으면 임시 삽입 위치 i를 삽입 원소의 위치로 확정하고 6번을 수행한다.
4. 삽입할 원소 item이 부모 노드보다 크면, 부모와 자식의 자리를 맞바꿔 최대 힙 관계를 만들어야 하므로 부모노드인 heap[i/2]을 현재 임시 삽입 위치 heap[i]에 저장
5. i/2를 임시삽입위치로 하여 2~5를 반복하면서 item을 삽입할 위치를 찾는다.
6. 찾은 위치에 삽입할 원소 item을 저장하면 최대 힙의 재구성 작업이 완성되므로 삽입 연산을 종료한다. 

## Deletion of Max Heap

![Untitled](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c/Untitled%201.png)

1. 루트 노드 hea[1]을 변수 item에 저장한다.
2. 마지막 노드의 원소 heap[n]을 변수 temp에 임시로 저장한다.
3. 마지막 노드를 삭제하였으므로 힙 배열의 원소 개수 하나 감소한다.
4. 마지막 노드 원소였던 temp의 임시 저장 위치 i는 루트 노드 자리인 1번이 된다.
5. 현재 저장 위치에서 왼쪽 자식 노드 heap[j]와 오른쪽 자식 노드 heap[j+1]이 있을 때, 키값이 큰 자식 노드의 키값과 temp를 비교하여 temp가 크거나 같으면 현재의 임시 저장 위치를 temp자리로 확정하고, 7번을 수행한다.
6. temp가 자식 노드 temp[j]보다 작으면 자식 노드와 자리를 바꾸고 5~6번을 반복하며 temp의 자리를 찾는다.
7. 찾은 위치에 temp를 저장, 최대 힙 재구성 작업을 완성한다.
8. 처음에 삭제된 루트 노드를 저장한 변수 item을 반환하고 삭제연산을 종료한다.

## C Code of Heap Sort

```c
#include <stdio.h>
#include <stdlib.h>
#define MAX_ELEMENT 100
typedef struct {    //make struct of one dimension array of heap and size of heap
    int heap[MAX_ELEMENT];
    int heap_size;
} heapType;
 
heapType* createHeap()        //make empty heap
{
    heapType *h = (heapType *)malloc(sizeof(heapType));
    h->heap_size = 0;
    return h;
}
 
void insertHeap(heapType *h, int item)    //insert item into heap
{
    int i;
    h->heap_size = h->heap_size + 1;
    i = h->heap_size;
    while ((i != 1) && (item > h->heap[i / 2])) {
        h->heap[i] = h->heap[i / 2];
        i /= 2;
    }
    h->heap[i] = item;
}
 
int deleteHeap(heapType *h)        //delete root of heap
{
    int parent, child;
    int item, temp;
    item = h->heap[1];
    temp = h->heap[h->heap_size];
    h->heap_size = h->heap_size - 1;
    parent = 1;
    child = 2;
    while (child <= h->heap_size) {
        if ((child <= h->heap_size) && (h->heap[child] < h->heap[child + 1]))
            child++;
        if (temp >= h->heap[child])    break;
        else {
            h->heap[parent] = h->heap[child];
            parent = child;
            child = child * 2;
        }
    }
    h->heap[parent] = temp;
    return item;
}
 
printHeap(heapType *h)    //print one dimension of heap
{
    int i;
    printf("Heap : ");
    for (i = 1; i <= h->heap_size; i++)
        printf("[%d]", h->heap[i]);
}
 
void main()
{
    int i, n, item;
    heapType *heap = createHeap();
    insertHeap(heap, 10);
    insertHeap(heap, 45);
    insertHeap(heap, 19);
    insertHeap(heap, 11);
    insertHeap(heap, 96);
 
    printHeap(heap);
 
    n = heap->heap_size;
    for (i = 1; i <= n; i++) {
        item = deleteHeap(heap);
        printf("\ndelete : [%d] ", item);
    }
 
    getchar();
}
```

# Shell Sort

## About Shell Sort

셸 정렬은 어느 정도 정렬 되어 있는 배열에 대해서는 삽입정렬이 대단히 빠르다는 점을 이용해 만든 방법으로서 삽입 정렬의 성질을 이용, 보완한 삽입정렬의 일반화로 볼 수 있다. 셸 정렬은 주어진 자료 리스트를 특정 매개변수 값의 길이를 갖는 부파일(subfile)로 쪼개서, 각 부파일에서 정렬을 수행한다. 즉, 매개변수 값에 따라 부파일(Subfile)이 발생하며, 매개변수값을 줄이며 이 과정을 반복하고 결국 매개변수 값이 1이면 정렬은 완성된다. 우선 데이터를 십수 개 정도 듬성듬성 나누어서 삽입 정렬한다. 그 다음, 데이터를 다시 잘게 나누어서 삽입 정렬한다. 첫 단계와 두번째 단계를 반복해나아가며 정렬을 완료한다. 

## C Code of Shell Sort

```c
// Shell Sort in C programming

#include <stdio.h>

// Shell sort
void shellSort(int array[], int n) {
  // Rearrange elements at each n/2, n/4, n/8, ... intervals
  for (int interval = n / 2; interval > 0; interval /= 2) {
    for (int i = interval; i < n; i += 1) {
      int temp = array[i];
      int j;
      for (j = i; j >= interval && array[j - interval] > temp; j -= interval) {
        array[j] = array[j - interval];
      }
      array[j] = temp;
    }
  }
}

// Print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

// Driver code
int main() {
  int data[] = {9, 8, 3, 7, 5, 6, 4, 1};
  int size = sizeof(data) / sizeof(data[0]);
  shellSort(data, size);
  printf("Sorted array: \n");
  printArray(data, size);
}
```

# Comparison of Comparison Based Sort

![Untitled](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c/Untitled%202.png)

위 도표를 보면 비교정렬의 목록과 각각의 비교정렬에 대한 평균의 시간복잡도, 최악의 시간 복잡도, 정렬 방법, 그리고 각각의 장담점을 파악할 수 있다. 버블정렬은 교환을 통해 정렬을 구현하며 직관적이고, 안정적이지만 평균과 최악의 경우가 모두 O(n^2)로 큰 테이블에 대해서는 비효율적이다. 삽입 정렬은 삽입을 통해 정렬을 구현하며 사전정렬되어있거나 작은 리스트 형태에 효율적이며, 메모리소비를 최소화하지만 큰 배열을 정렬할 때는 느리다. 선택정렬은 선택을 통해 정렬을 구현하며 버블 정렬의 효율성을 높였지만 느리고, 큰 규모의 데이터에는 느리다는 단점이 존재한다. 힙 정렬은 선택을 통해 정렬을 구현한 알고리즘 중 가장 효율적인 버전으로서 추가적인 버퍼가 필요하지 않으며, 재귀호출을 할 일이 없어 퍼포먼스 측면에서 좋으며, 퀵 정렬과 병합 정렬보다는 느리다. 병합 정렬은 병합을 통해 정렬을 구현하며 안정적인 정렬에 속하고, 큰 규모의 리스트 정렬 시 효과적이다. [[8]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

# Criteria for Choosing a Sort Algorithm

![Untitled](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c/Untitled%203.png)

위 도표는 어떠한 상황에 있어 정렬 알고리즘을 써야하는지에 대한 분류표이다. 삽입정렬은 데이터 갯수가 적을 때와 사전정렬이 되어있을 때 유리하며, 힙 정렬은 최악의 경우가 걱정될 때 쓰이면 좋다. 또한 평균의 경우에 대한 좋은 결과 얻고 싶을 때는 퀵 정렬을 사용하는 것이 좋으며, 데이터의 밀집도가 높은 경우에는 버킷 정렬이, 최소한의 코드로 정렬을 하고 싶을 때는 삽입 정렬이 좋다. [[9]](Report%20Sorting%20Algorithms%20004f7febb0d84e5c8d971e360402d52c.md)

# Conclusion

본 보고서는 대표적으로 쓰이는 정렬 알고리즘 10가지에 대해 정의와 특징, 코드들에 대한 설명을 나열하였다. 이를 통해 어떠한 경우에 정렬을 쓰는지, 어떤 단점들이 있는지, 각각의 시간복잡도는 어떠한 지에 대해 기술할 수 있으며, 상황에 맞는 알고리즘을 적용할 수 있다.

향후 더욱 다양한 정렬 알고리즘에 대한 공부 및 연구를 통해 각 경우에 맞는 정렬을 구현 혹은 적용을 할 수 있을 것이다.

# Reference

1. 손명준, 이형옥. (2022). 정렬 알고리즘 시뮬레이션을 위한 학습 프로그램. 한국컴퓨터교육학회 학술발표대회논문집, 26(1), 49 page
2. Ani Kristo, Kapil Vaidya, Ugur Çetintemel, Sanchit Misra, and Tim Kraska,“The Case for a Learned Sorting Algorithm”, SIGMOD '20: Proceedings of the 2020 ACM SIGMOD International Conference on Management of Data.
3. Rouf Ali,Jammu & Kashmir, India, “Sorting and Classification of Sorting Algorithms” Classification of Sorting Algorithms, Turkish Journal of Computer and Mathematics Education Vol.12 No.14 (2021), 5920-5924
4. Dr. Fang Tang,Computer Science Department,California State Polytechnic University, Pomona, “Introduction to Sorting Algorithm”
5. 이지영 저, C로 배우는 쉬운 자료구조, Ch09 정렬, 한빛미디어 16년7월28일
6. Ramesh Chand Pandey, Study and Comparison of Various Sorting Algorithms,
COMPUTER SCIENCE AND ENGINEERING DEPARTMENT THAPAR UNIVERSITY , JULY 2008
7. 이지영 저, C로 배우는 쉬운 자료구조, Ch07 트리, 한빛미디어 16년7월28일
8. Aditya Dev Mishra and Deepak Garg, "Selection of Best Sorting Algorithm",
International Jornal of Intelligent Information Processing
2(2) July-December 2008;pp. 363-368
9. Prof. Kevin Amaratunga , “Foundations of Software Engineering” Course, Sorting Performance Criteria