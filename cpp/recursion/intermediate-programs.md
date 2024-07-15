# Intermediate Programs
1. [Print subsequences of given array](#Print-subsequences-of-given-array)
2. [Print subsequences whose sum equals to k](#Print-subsequences-whose-sum-equals-to-k)


#### 1. Print subsequences of given array
```cpp
#include <bits/stdc++.h>
void subSeq(std::array<int, 3> &arr, int index, int n, std::vector<int> &list)
{
    if (index == n) {
        for (auto &itr: list)
            std::cout<< itr;
        if(list.size() == 0) std::cout<< "{}";
        std::cout<<std::endl;
        return;
    }
    list.push_back(arr[index]);
    subSeq(arr, index + 1, n, list);
    list.pop_back();
    subSeq(arr, index + 1, n, list);
}

int main()
{
    std::array<int, 3> arr {3, 1, 2};
    std::vector<int> list;
    subSeq(arr, 0, arr.size(), list);
}
```

#### 2. Print any subsequence whose sum equals to k
```cpp
#include <bits/stdc++.h>
bool subSeqSum(std::array<int, 3> &arr, int index, int n, std::vector<int> &list, int sum, int k)
{
    if(index == n) // base condition
    {
        if (sum == k) {
        for(auto &itr: list)
            std::cout<< itr;
         std::cout<<std::endl;
           return true;
        }
        return false;
    }
    list.push_back(arr[index]);
    sum = sum + arr[index];
    if(subSeqSum(arr, index + 1, n, list, sum, k) == true) return true;
    sum = sum - arr[index];
    list.pop_back();
    if(subSeqSum(arr, index +1, n, list, sum, k)  == true) return true;
    return false;
}

int main()
{
    std::array<int, 3> arr { 1, 1, 1};
    std::vector<int> list;
    int k = 3;
    std::cout<<"Subsequences whose sum is equal to k are "<< std::endl;
    subSeqSum(arr, 0, arr.size(), list, 0, k);
}
```
