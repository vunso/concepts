# Beginner Programs
- [Print linearly from 1 to `N`](#Print-linearly-from-1-to-N)
- [Print linearly from `N` to 1](#Print-linearly-from-N-to-1)
- [Factorial of number provided by user](#Factorial-of-number-provided-by-user)
- [Reverse elements of array](#Reverse-elements-of-array)
- [Nth Fibonacci number](#Nth-Fibonacci-number)

#### Print linearly from 1 to `N`
```cpp
void func(int i, int n)
{
    if (i > n) return; //base condition
    std::cout << i << std::endl;
    func(i + 1, n);
}
int main()
{
    int n;
    std::cin >> n;
    func(1, n);
}
// Time complexity: O(N), Space Complexity O(N)
```

#### Print linearly from `N` to 1
```cpp
void func(int i, int n)
{
    if (i > n) return; //base condition
    func(i + 1, n);
    std::cout << i << std::endl;
}
int main()
{
    int n;
    std::cin >> n;
    func(1, n);
}
// Time complexity: O(N), Space Complexity O(N)
```

#### Factorial of number provided by user
```cpp
int factorial(int n)
{
    if (n == 1) return 1; // base condition
    return n * factorial(n-1);
}
int main()
{
    int n;
    std::cin >> n;
    std::cout <<"Reuslt of factorial of "<< n <<" is " << factorial(n);
}
// Time complexity: O(N), Space Complexity O(N)
```

#### Reverse elements of array
```cpp
void swapArray(int arr[], int left, int right)
{
    if (left >= right) return; // base condition
    std::swap(arr[left], arr[right]);
    swapArray(arr, left+1, right-1);
}
int main()
{
    int arr[5] = {1, 3, 5, 7, 9};
    swapArray(arr, 0, sizeof(arr)/sizeof(int)-1);
    for(auto &itr : arr)
        std::cout<<itr <<" ";
}
```

#### Nth Fibonacci number
```cpp
int fibo(int n)
{
    if(n <= 1) return n;
    return fibo(n - 1) + fibo(n -2);
}
int main()
{
    std::cout << fibo(8);
}
```
 Time complexity: O(2<sup>n</sup>), Space Complexity  O(2<sup>n</sup>)