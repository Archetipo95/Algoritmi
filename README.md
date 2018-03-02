# Algoritmi

Una raccolta degli algoritmi in pseudo python (NB array partono da 1)

[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://opensource.org/licenses/Apache-2.0) [![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

## Indice

- [Insertion Sort](#insertion-sort)
- [Credits](#credits)


# Insertion Sort

`Input: A[1,...,n]`

```python
insertionSort(A[])
	for i=2 to n	# il primo elemento è già ordinato
		key = A[i]	# A[1..i-1] ordinato
		j = i-1
		while j>0 and A[j]>key
			A[j+1] = A[j]
			j = j-1
		A[j+1] = key
```

Il **while** termina se:

	1. j=0 -> tutti gli elementi prima di i sono maggiori di key -> key va al primo posto A[1]
	2. j>0 AND A[j]<=key -> A[j+1]=key
	


![Alt Animated GIF of the insertion sort](https://upload.wikimedia.org/wikipedia/commons/4/42/Insertion_sort.gif)
![Alt Graphical example of the insertion sort](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

[Wikipedia Link](https://en.wikipedia.org/wiki/Insertion_sort "Insertion Sort link to Wikipedia")

# Credits

* [Vashy](https://github.com/Vashy)'s [ASD-Notes](https://github.com/Vashy/ASD-Notes) repository
* [Wikipedia](https://en.wikipedia.org)
