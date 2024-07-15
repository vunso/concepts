### 1. Selection Sort

- **Select minimum and swap**
- **Time complexity O(n^2) for worst,average and best case**
- **Space complexity 0(1)**

```cpp
#include <bits/stdc++.h>

void selectionSort(std::array<int, 9> &arr)
{
    int n = arr.size(), mini;
    for(int i = 0; i < n - 1 ; i++) {
        mini = i;
        for(int j = i + 1; j < n; j++)
        {
            if(arr[mini] > arr[j])
                mini = j;
        }
        if(i != mini)
          std::swap(arr[i], arr[mini]);
    }
}

int main()
{
    std::array<int, 9> arr { 9, 8, 7, 6, 5, 4, 3, 2, 1};
    std::cout<<"Array before sorting " << std::endl;
    for(auto &itr: arr){
        std::cout<< itr <<" ";
    }
    selectionSort(arr);
    std::cout<<std::endl<<"Array after sorting " << std::endl;
    for(auto &itr: arr){
        std::cout<< itr <<" ";
    }
}
```

### 2. Bubble Sort - Time complexity O(n^2)

- **Push maximum to the last by adjacent swaps**
- **Time complexity O(n^2) for worst,average case and  O(n) best case**
- **Space complexity 0(1)**
```cpp
#include <bits/stdc++.h>

template <std::size_t N>
void bubbleSort(std::array<int, N> &arr)
{
    int n = arr.size();
    for (int i = 0; i < n - 1; i++) {
        bool swapped = false;
        for(int j = 0; j < n - i - 1; j++) {
            if(arr[j] > arr[j+1]) {
                std::swap(arr[j], arr[j+1]);
                swapped = true;
            }
        }
        // If none of elements are swapped we break loop
        if (swapped == false)
            break;
    }
}

int main()
{
    std::array arr { 9, 8, 7, 6, 5, 4, 3, 2, 1};
    std::cout<<"Array before sorting " << std::endl;
    for(auto &itr: arr){
        std::cout<< itr <<" ";
    }
    bubbleSort(arr);
    std::cout<<std::endl<<"Array after sorting " << std::endl;
    for(auto &itr: arr){
        std::cout<< itr <<" ";
    }
}

```

### 3. Insertion Sort  - Time complexity O(n^2)

- **Takes element and places it in its correct order**
- **Time complexity O(n^2) for worst,average case and  O(n) best case**
- **Space complexity 0(1)**
```cpp
#include <bits/stdc++.h>

void insertionSort(int arr[], int size)
{
    for(int i = 1; i < size ; i++)
    {
        int j = i;
        while (j > 0 && arr[j] < arr[j-1]){
            std::swap(arr[j], arr[j-1]);
            j--;
        }
    }
}
int main()
{
    int arr[] = { 99, 88, 77, 55, 11, 33, 22, 1, 100};
    std::cout<<"Array before sorting" << std::endl;
    for(auto itr: arr)
        std::cout<<itr<<" ";
    insertionSort(arr, sizeof(arr)/sizeof(arr[0]));
    std::cout<<std::endl<<"Array after sorting" << std::endl;
    for(auto itr: arr)
        std::cout<<itr<<" ";
}
```