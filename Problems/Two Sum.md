[Two Sum](https://leetcode.com/problems/two-sum/)

#Easy #Arrays 

---
## Strategy 1 - Brute Force

For elements $e_1$ and $e_2$ in the array, check if $e_1 + e_2 == target$. Hence, check all possible pairwise sums of two elements in the array.

##### Time complexity - 

$\mathcal{O}(N^2)$

If $t$ is the time taken for $1$ basic step (_sum of two elements_ and comparison with _target_), and the size of the array is $N$, then the total time $T$ is given by (indexing starts from $1$), 

$$ \begin{align} T & = \sum_{i=1}^{N - 1} \sum_{j = i+1}^{N} t \\ & = t \sum_{i=1}^{N - 1} (N - (i+1) + 1) \\ & = t \sum_{i=1}^{N - 1} (N - i) \\ & = t [(N-1) + (N-2) + \ldots + 2 + 1] \\ & = t \frac{(N - 1) N}{2} \\ T & = \frac{t N^2}{2} - \frac{tN}{2} = \mathcal{O}(N^2)
\end{align} $$

##### Space complexity - 

$\mathcal{O}(1)$

There is only constant extra space being used -
- To compute the sum 
- Perform comparison

Hence, space complexity is $\mathcal{O}(1)$.

--- 
## Strategy 2

Use a [[Hash map]] to store the elements of the array, so that for later element $e$ , if $target - e$ exists in the hash map, return the result. 

	The advantage is based on the principle that finding an element in the hash map is O(1) operation (amortized complexity).

##### Time complexity - 

$\mathcal{O}(N)$

The `insert` operation in hash map is $\mathcal{O}(1)$. The total time $T$ is given by,

$$ \begin{align} T & = \sum_{i=1}^{N} t \\ T  & = tN = \mathcal{O}(N) \end{align} $$

##### Space complexity - 

$\mathcal{O}(N)$

In the worst case, all elements will be stored in the hash map. Hence, a hash map of size $N$ is required. Thus, the space complexity is $\mathcal{O}(N)$.