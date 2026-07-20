# DSA Patterns — Week 4 Module

Complexity analysis of pattern programs, searching/sorting basics, and advanced sorting algorithms (Merge, Quick, Heap Sort), along with solved coding problems.

---

## 📂 Module 1 — Pattern Programs (Complexity Analysis)

| Pattern | Time Complexity | Space Complexity | Optimized Further? |
|---|---|---|---|
| Square Pattern | O(N²) | O(1) | No — output size itself is N² |
| Hollow Square | O(N²) | O(1) | No |
| Right Triangle | O(N²) | O(1) | No — already minimal |
| Inverted Triangle | O(N²) | O(1) | No |
| Pyramid | O(N²) | O(1) | No |
| Diamond / Half Diamond | O(N²) | O(1) | No |
| Number Patterns (general) | O(N²) | O(1) | No — inherent to output size |

**Key takeaway:** All pattern programs use nested loops bounded by `N`, giving `O(N²)` time. Since the number of characters printed is proportional to `N²`, this complexity is *inherent* to the problem — not something further optimization can reduce. Space stays `O(1)` since only loop counters are used.

---

## 📂 Module 2 — Searching & Sorting Basics

### Linear Search
- **Time:** O(N) — worst case checks every element once
- **Space:** O(1)
- **Optimization:** Use Binary Search (O(log N)) if the array is sorted; otherwise Linear Search is optimal for unsorted data.

### Binary Search
- **Time:** O(log N) — each iteration halves the search range
- **Space:** O(1) (iterative version — no recursion stack)
- **Optimization:** Already optimal; O(log N) is the theoretical lower bound for comparison-based search on sorted data.

### Bubble Sort
- **Time:** O(N²) worst/average, O(N) best case (with early-exit swap flag on a sorted array)
- **Space:** O(1) — in-place sort
- **Optimization:** Use Merge Sort or Quick Sort (O(N log N)) for large, unsorted datasets.

### Selection Sort
- **Time:** O(N²) in all cases — always scans remaining elements to find the minimum
- **Space:** O(1)
- **Optimization:** Merge Sort / Heap Sort (O(N log N)) are preferable since Selection Sort always does a full scan regardless of input order.

### Insertion Sort
- **Time:** O(N²) worst/average, O(N) best case (already sorted)
- **Space:** O(1)
- **Optimization:** Merge Sort is better for large datasets; Insertion Sort remains efficient for small or nearly-sorted arrays.

---

## 📂 Module 3 — Merge Sort, Quick Sort, Heap Sort

### Merge Sort
- **Time:** O(N log N) in all cases — recursive split (log N depth) × O(N) merge work per level
- **Space:** O(N) — temporary array for merging
- **Optimization:** Heap Sort (avoids extra space)

### Quick Sort
- **Time:** O(N log N) average, O(N²) worst case (poor pivot choices)
- **Space:** O(log N) average, O(N) worst case (recursion stack)
- **Optimization:** Randomized pivot selection avoids worst-case O(N²) on already-sorted inputs, keeping expected complexity at O(N log N).

### Heap Sort
- **Time:** O(N log N) in all cases — O(N) to build the heap + N × O(log N) extractions
- **Space:** O(1) — operates in-place
- **Optimization:** Already achieves optimal time and space complexity among the three.

---

## 📊 Complexity Summary Table

| Algorithm | Best | Average | Worst | Space |
|---|---|---|---|---|
| Patterns | O(N²) | O(N²) | O(N²) | O(1) |
| Linear Search | O(1) | O(N) | O(N) | O(1) |
| Binary Search | O(1) | O(log N) | O(log N) | O(1) |
| Bubble Sort | O(N) | O(N²) | O(N²) | O(1) |
| Selection Sort | O(N²) | O(N²) | O(N²) | O(1) |
| Insertion Sort | O(N) | O(N²) | O(N²) | O(1) |
| Merge Sort | O(N log N) | O(N log N) | O(N log N) | O(N) |
| Quick Sort | O(N log N) | O(N log N) | O(N²) | O(log N) – O(N) |
| Heap Sort | O(N log N) | O(N log N) | O(N log N) | O(1) |

---

## 💻 Solved Problems

### Problem 1: Print 1 to N
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    for (int i = 1; i <= n; i++) {
        cout << i;
        if (i != n) cout << " ";
    }
    cout << endl;
    return 0;
}
```
- **Time:** O(N) — single pass over input size
- **Space:** O(1)
- **Optimized:** Already optimal

### Problem 2: Sum of First N Natural Numbers
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    long long sum = 0;
    for (int i = 1; i <= n; i++) {
        sum += i;
    }
    cout << sum << endl;
    return 0;
}
```
- **Time:** O(N)
- **Space:** O(1)
- **Optimized:** Yes — can be computed in O(1) using the formula `N*(N+1)/2`

### Problem 3: A^B Using a Loop
```cpp
#include <iostream>
using namespace std;

int main() {
    long long a, b;
    cin >> a >> b;

    long long result = 1;
    for (int i = 1; i <= b; i++) {
        result *= a;
    }
    cout << result << endl;
    return 0;
}
```
- **Time:** O(B) — loop runs exactly `B` times, work scales with the exponent, not the base
- **Space:** O(1)
- **Optimized:** Yes — can be reduced to O(log B) using fast/binary exponentiation

---

## 🛠 Tech Stack
- **Language:** C++
- **Compiler/Editor:** VS Code

---

*Notes compiled from handwritten DSA module (Week 4).*
