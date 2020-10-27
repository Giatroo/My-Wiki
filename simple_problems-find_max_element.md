## The max

**Problem:** Given a vector $A$, with $n>0$ elements, find its maximum element
and return its index.

**Algorithm:**

```cpp
int find_max(int *A, int n) {
    int cur_max = 0;
    for (int i = 1; i < n; i++)
        if (A[i] > A[cur_max])
            cur_max = i;
    return i;
}
```

**Time:** $O(n)$

**Espace:** $O(1)$

## Two max values

**Problem:** Given a vector A, with n > 1 elements, find its maximum element and
its second maximum element and return their indexes.

```cpp
void find_two_maxs(int *A, int n, int &first, int &second) {
    first = 0;
    second = -1;

    for (int i = 1; i < n; i++) {
        if (A[i] > A[first]) {
            second = first;
            first = i;
        } else if (A[i] > A[second]) {
            second = i;
        }
    }
}
```
