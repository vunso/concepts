## What is the recursion?
**When the function call itself untill specified is met.** <br>

#### If base condition not met it may result in stack overflow as in example below
```
void func()
{
    std::cout <<"Hello World" << std::endl;
}
int main()
{
    func()
}
```

### What is recursion tree ?
A recursion tree is useful for visualizing what happens when recurrence is iterated.


### Subsequence
A contigous or non-contigous sequences which follows the order.