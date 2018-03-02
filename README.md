# Algoritmi

Una raccolta degli algoritmi in pseudo codice

[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://opensource.org/licenses/Apache-2.0) [![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

## Indice

- [Insertion Sort](#insertion-sort)

# Insertion Sort

Input: A[1,...,n], A.length

```python {.line-numbers}
	n = A.length
	for j=2 to n
	key = A[j]
	i = j-1
	while i>0 and A[i]>key
		A[i+1] = A[i]
		i = i-1
	A[i+1] = key
```