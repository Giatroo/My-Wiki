## Computing Fibonacci Numbers

We're going to use Dynamic Programming:

```cpp
int F(int n) {
    int n2 = 0;
    int n1 = 1;
    int n;

    for (int i = 2; i <= n; i++) {
        n = n1 + n2;
        n2 = n1;
        n1 = n;
    }
    return n;
}
```
