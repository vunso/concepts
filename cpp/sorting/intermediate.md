### 1. Merge Sort

- **Divide and merge**
- **Time complexity O(n log(n)) for worst,average and best case**
- **Space complexity 0(n)**

```cpp
#include <bits/stdc++.h>

void merge(std::vector<int> &arr, int low, int mid, int high)
{
    std::vector<int> temp;
    int left = low, right = mid + 1;
    while(left <= mid && right <= high)
    {
        if(arr[left] <= arr[right])
            temp.push_back(arr[left++]);
        else
            temp.push_back(arr[right++]);
    }
    while(left <=  mid)
        temp.push_back(arr[left++]);

    while(right <= high)
        temp.push_back(arr[right++]);

    for(int i = low; i <= high; i++)
        arr[i] = temp[i - low];
}

void mergeSort(std::vector <int> &arr, int low, int high)
{
    if(low >= high) return; //base condition
    int mid = (low + high) / 2;
    mergeSort(arr, low, mid); // left half of teh array
    mergeSort(arr, mid + 1, high); // right half of the array
    merge(arr, low, mid, high);

}
int main()
{
    std::vector<int> arr = { 7, 9, 1, 3, 2, 8, 6};
    std::cout<<"Array before sorting " << std::endl;
    for(auto itr: arr)
        std::cout<<itr <<" ";
    mergeSort(arr, 0, arr.size() - 1);
    std::cout<<std::endl<<"Array after sorting " <<std::endl;
    for(auto itr: arr)
        std::cout<<itr<< " ";
}
```

### 2. Quick Sort

- **Divide and merge**
- **Time complexity O(n log(n)) for average,best case and O(n^2) for worst case**
- **Space complexity O(log(n))**
```cpp
#include <bits/stdc++.h>

int partition(int arr[], int low, int high)
{
    int pivot = arr[low], i = low, j = high;
    while(i < j) {
        while(pivot >= arr[i] && i<= high - 1) i++;
        while(pivot < arr[j] && j>= low + 1) j--;
        if(i < j) std::swap(arr[i], arr[j]);
    }
    std::swap(arr[low], arr[j]);
    return j;
}
void quickSort(int arr[], int low, int high)
{
    if(low < high) {
        int part = partition(arr, low, high);
        quickSort(arr, low, part - 1);
        quickSort(arr, part + 1, high);
    }
}
int main()
{
    int arr[] = {9, 8, 7, 6, 5, 4, 3, 2};
    quickSort(arr, 0, sizeof(arr)/sizeof(arr[0]) - 1);
    std::cout<<"Array after sorting "<< std::endl;
    for(auto itr: arr)
        std::cout<<itr<<" ";
}
```
