# MinHash Exercise

## Description

This repository contains an implementation of **MinHash**, a probabilistic technique used to efficiently estimate the similarity between sets.

The exercise focuses on understanding **Jaccard similarity**, MinHash signatures, and how hashing can be used to compare large collections of data efficiently.

## Learning Objectives

The main goals of this exercise are to:

- Understand **Jaccard similarity**
- Represent documents as sets of elements or shingles
- Generate MinHash signatures
- Estimate similarity between sets using MinHash
- Understand the relationship between exact Jaccard similarity and MinHash similarity
- Explore the efficiency of probabilistic similarity estimation

## Jaccard Similarity

The Jaccard similarity between two sets \(A\) and \(B\) is defined as:

```text
J(A, B) = |A ∩ B| / |A ∪ B|
```

The value ranges from `0` to `1`:

- `0` means the sets have no elements in common.
- `1` means the sets are identical.

For example:

```text
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}
```

The intersection is:

```text
A ∩ B = {3, 4}
```

and the union is:

```text
A ∪ B = {1, 2, 3, 4, 5, 6}
```

Therefore:

```text
J(A, B) = 2 / 6 = 0.333
```

## MinHash

MinHash creates a compact **signature** for each set.

Instead of comparing every element in two sets directly, multiple hash functions are applied to the elements. For each hash function, the minimum hash value is stored.

The resulting signature can be used to estimate Jaccard similarity:

```text
Estimated Jaccard Similarity
≈
Number of matching signature values
/
Total number of hash functions
```

The more hash functions used, the more accurate the estimate generally becomes.

## Example

Consider two sets:

```text
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}
```

After applying a collection of hash functions, we might obtain:

```text
Signature A = [2, 1, 5, 3, 4]
Signature B = [2, 4, 5, 6, 1]
```

The signatures match in 2 out of 5 positions.

Therefore, the estimated similarity is:

```text
2 / 5 = 0.4
```

The estimate may differ from the exact Jaccard similarity because MinHash is probabilistic.


## Project Structure

```text
.
├── README.md
├── src/
│   └── minhash.*
├── exercises/
│   ├── exercise1/
│   ├── exercise2/
│   └── exercise3/
└── tests/
    └── ...
```

eated for educational purposes.
