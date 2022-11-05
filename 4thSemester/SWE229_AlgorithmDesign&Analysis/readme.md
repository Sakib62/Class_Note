<h1 align="center"> Algorithm Design and Analysis </h1>

<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1ZwZHAAirbBEvp0mxAs3urO2tOawbSw1N" title="Drive Link of Algo">Drive Link</a></h3>

[DP Resource](https://bit.ly/dpseriestuf)

<details><summary><h2>Syllabus</h2></summary>
<blockquote> <p>
Sieve - Bitwise, Segmented, Linear<br>
Divisor - Count, Sum<br>
Phi<br>
Modular Inverse - with Power, with Ext. Euclid<br>
CRT - Ext. Euclid

Floyd Warshall<br>
Bellman Ford<br>
Heapsort - Heap<br>
Counting Sort, Radix Sort, Bucket Sort<br>
Order Statistics<br>
Hash Table<br>
Binary Search Tree<br>
Balance Binary Search Tree - Treap / AVL Tree

DP - Matrix Chain Multiplication, Knapsack, CoinChange<br>
Greedy - Task Scheduling<br>
Max Flow - Ford Fulkerson

String Matching - KMP, Rabin Karp (Hashing)<br>
Suffix Array<br>
Strongly Connected Component

FFT* (probably)

Quicksort*, DSU*, MST*, Dijkstra*, DFS*, BFS* (covered in CP course)
</p></blockquote>
</details>

<details><summary><h2>Lecture-01: 23th August, 2022</h2></summary>

1. Sieve of Eratosthenes
2. Linear Sieve
</details>

<details><summary><h2>Lecture-02: 28th August, 2022</h2></summary>

1. Bitwise Operation
2. Bitwise Sieve
</details>

<details><summary><h2>Lecture-03: 30th August, 2022</h2></summary>

1. Segmented Sieve
</details>

<details><summary><h2>Lecture-04: 4th September, 2022</h2></summary>

1. Euler phi
1. Count of Divisor
2. Sum of Divisor
3. Prime in cube root complexity, N = P * Q * R, Miler Rabin
</details>

<details><summary><h2>Lecture-05: 6th September, 2022</h2></summary>

1. BigMod / Modular Exponentiation
2. Extended Euclid
3. Modular Multiplicative Inverse
4. Fermat's Little Theorem

https://cp-algorithms.com/algebra/extended-euclid-algorithm.html
</details>

<details><summary><h2>Lecture-06: 11th September, 2022</h2></summary>

1. Shortest Path 
2. Floyd Warshall
</details>

<details><summary><h2>Lecture-07: 18th September, 2022</h2></summary>

1. Bellman Ford
2. Chinese Remainder Theorem
</details>

<details><summary><h2>Lecture-08: 20th September, 2022</h2></summary>

1. Chinese Remainder Theorem (Code of Weak Form + Strong Form discussion)
</details>

<details><summary><h2>Lecture-09: 25th September, 2022</h2></summary>

1. Heap Sort (Heapify & Sorting)
</details>

<details><summary><h2>Lecture-10: 16th October, 2022</h2></summary>

<h3><b>Counting Sort</b></h3>

1. Not comparison based.<br>Stable Sorting Algorithm -> Important if number is associated with something.<br><br>
Stability of sorting algorithm simply means that<br> the relative ordering of elements with same keys will remain same before & after the sorting.<br><br>
1. Particular Range
2. Initialize count array for elements
3. Frequency table (index sorted, so no comparison)
4. Cumulative sum //*Can find sorted array from this part too.*
5. From reverse to ensure stable sort
    ```cpp
    for(int i = n-1; i >= 0; i--) {
        output[count[arr[i]] - 1] = arr[i]
        count[arr[i]]--; //If same number repeats, order will be same
    }
    ```
6. Complexity: O(n+k), k is range for cumulative sum

    <details><summary>Code:</summary>

    ```cpp
    //Bismillahir Rahman-ir Rahim
    #include <bits/stdc++.h>
    using namespace std;

    void countSort(int *a, int n) {
        int mx = *max_element(a, a+n); //to determine range of freq array
        int freq[mx + 1] = {0}, ans[n];

        for(int j = 0; j < n; j++) { //frequency array
            freq[a[j]]++;
        }
        for(int j = 1; j < mx + 1; j++) { //prefix sum
            freq[j]+=freq[j-1]; //can complete sorting in this point though won't be stable
        }
        //from last to make stable sorting
        for(int i = n - 1; i >= 0; i--) {
            ans[freq[a[i]] - 1] = a[i];//-1 to fit in 0 based indexing. a[i] is freq[a[i]]th element if sorted
            freq[a[i]]--;//already placed this one, hence decrement
        }
        //copy into original array
        for(int i = 0; i < n; i++) {
            a[i] = ans[i];
        }
    }

    void solve() {
        int n;
        cin >> n;
        int a[n];
        for(int i = 0; i < n; i++) {
            cin >> a[i];
        }
        countSort(a, n);
        for(int i = 0; i < n; i++) {
            cout << a[i] << " ";
        }
        cout << "\n";
    }

    int main() {
        ios_base::sync_with_stdio(false); cin.tie(0); int testCase = 1;
        //cin >> testCase;
        while(testCase--) {
            solve();
        }
    }
    ```
    </details>
</details>

<details><summary><h2>Lecture-11: 18th October, 2022</h2></summary>

1. Some primary info about Git operation.
2. Pull Request, Fork, Collaborations.
3. Sublime Merge

</details>

<details><summary><h2>Lecture-12: 23th October, 2022</h2></summary>

1. Radix Sort
2. Bucket sort

</details>

<details><summary><h2>Term Test-1: 26th October, 2022</h2></summary>

*Pseudo Code/Algorithm/Code*

- Sieve & variations
- Extended Euclid Algorithm
- Modular Multiplicative Inverse
- Chinese Remainder Theorem
- Bellman Ford Algorithm
- Floyd Warshall Algorithm

<img src="assets\TT1.jpg" width="60%" height="10%">

</details>

<h2>Lecture-13: 30th October, 2022</h2>

ALgo, Complexity Analysis

1. Merge Sort 
2. Quick Sort

<h2>Lecture-14: 6th November, 2022</h2>