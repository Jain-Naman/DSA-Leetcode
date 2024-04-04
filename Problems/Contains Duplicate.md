[Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)

#Easy #Arrays 

---

## Strategy 1 - Brute Force

- **Leads to _TLE_ in Leetcode** 

For elements $e_1$ and $e_2$ in the array, check if $e_1 == e_2$. Hence, check all possible pairwise  elements in the array.

##### Time complexity - 

$\mathcal{O}(N^2)$

If $t$ is the time taken for $1$ basic step, and the size of the array is $N$, then the total time $T$ is given by (indexing starts from $1$), 

$$ \begin{align} T & = \sum_{i=1}^{N - 1} \sum_{j = i+1}^{N} t \\ & = t \sum_{i=1}^{N - 1} (N - (i+1) + 1) \\ & = t \sum_{i=1}^{N - 1} (N - i) \\ & = t [(N-1) + (N-2) + \ldots + 2 + 1] \\ & = t \frac{(N - 1) N}{2} \\ T & = \frac{t N^2}{2} - \frac{tN}{2} = \mathcal{O}(N^2)
\end{align} $$

##### Space complexity - 

$\mathcal{O}(1)$

There is only constant extra space being used -
- Perform comparison

Hence, space complexity is $\mathcal{O}(1)$.

---

## Strategy 2

Use a [[Hash map]] to store elements of the array. If there is a collision (for some key, the value is _not empty_), return `true` else return `false`.

##### Time complexity -

$\mathcal{O}(N)$

The total time $T$ is given by,
$$ \begin{align} T & = \sum_{i=1}^{N} t \\ T  & = tN = \mathcal{O}(N) \end{align} $$

##### Space complexity -

$\mathcal{O}(N)$

In the worst case, all elements will be stored in the hash map. Hence, a hash map of size $N$ is required. Thus, the space complexity is $\mathcal{O}(N)$.

---

## Strategy 3

Use [[Sorting]] to bring order in the array. Then compare consecutive elements and return `true` is they are equal.

##### Time complexity

Sorting - $\mathcal{O}(N \log N)$

Total time taken,

$$ \begin{align} T & = \mathcal{O}(N \log N) + N \\ & = \mathcal{O}(N \log N) \end{align} $$
##### Space complexity

Depends on the sorting algorithm!

- Quicksort has a space complexity of $\mathcal{O}(\log N)$ in average case, but can be $\mathcal{O}(N)$ in the worst case.