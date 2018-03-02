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
		key = A[i]  # numero da "ordinare"
		z = i-1     # A[1..i-1] ordinato, i-1 indice ultimo numero ordinato
		while z>0 and A[z]>key
			A[z+1] = A[z]
			z = z-1
		A[z+1] = key
```

`Output: A[1,...,n] ordinato`

Il **while** termina se:

1. `z = 0` -> tutti gli elementi prima di **i** sono maggiori di **key** -> **key** va al primo posto `A[1]`
2. `z > 0 AND A[z] <= key` -> `A[z+1] = key`
	
**Invarianti e corretteza**

- **for** `A[1. .i-1]` è ordinato e contiene gli elementi in `(1,i-1)` iniziali
- **while**	`A[1. .z]A[z+2. .i]` ordinato e `A[z+2. .i] > key`</br>
	In uscita abbiamo:
	- `i = n+1`;
	- `A[1. .n]` ordinato, come da invariante: vale `A[1. .i-1]` ordinato, e **i** vale `n+1`

![Alt Animated GIF of the insertion sort](https://upload.wikimedia.org/wikipedia/commons/4/42/Insertion_sort.gif)
![Alt Graphical example of the insertion sort](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

[Wikipedia Link](https://en.wikipedia.org/wiki/Insertion_sort "Insertion Sort link to Wikipedia")

# Credits

* [Vashy](https://github.com/Vashy "Link to Vashy's GitHub profile")'s [ASD-Notes](https://github.com/Vashy/ASD-Notes "Link to ASD-Notes") repository
* [Wikipedia](https://en.wikipedia.org "Wikipedia")
