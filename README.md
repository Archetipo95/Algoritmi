# Algoritmi

Una raccolta degli algoritmi in pseudo python (NB array partono da 1)

[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://opensource.org/licenses/Apache-2.0) [![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

## Indice

- [Insertion Sort](#insertion-sort)
- [Merge Sort](#merge-sort)
- [Credits](#credits)


# Insertion Sort

incrementale

`Input: A[1,...,n]`

```python
insertionSort(A[])
	for i=2 to n	  # il primo elemento è già ordinato
		key = A[i]	# numero da "ordinare"
		z = i-1	   # A[1..i-1] ordinato, i-1 indice ultimo numero ordinato
		while z>0 and A[z]>key
			A[z+1] = A[z]
			z--
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
	
**Costi**

- Avg: O(n^2)
- Worst: A ordinato in modo inverso -> O(n^2)
- Best: A ordinato -> O(n)

![Alt Animated GIF of the insertion sort](https://upload.wikimedia.org/wikipedia/commons/4/42/Insertion_sort.gif)
![Alt Graphical example of the insertion sort](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

[Wikipedia Link](https://en.wikipedia.org/wiki/Insertion_sort "Insertion Sort link to Wikipedia")

# Merge Sort

Dividi et Impera

**Legenda del codice**

* `A[i..n]` array di partenza con indice di scorrimento **k**
* **subAi**  indice inizio sottoarray di **A**
* **subAf** indice di fine sottoarray di **A**
* **subH** indice posizione centrale sottoarray di **A** (half)
* **n1** lunghezza parte di sinistra del sottoarray **L** con indice di scorrimento **i**
* **n2** lunghezza parte destra del sottoarray **R** con indice di scorrimento **z**

`Input: A[1,...,n],subAi,subAf`

```python
mergeSort(A[],subAi,subAf)
	if(subAi<subAf)            # ci sono almeno 2 elementi?
		subH = (subAi+subAf)/2 # intero più piccolo
		mergeSort(A[],subAi,subH)
		mergeSort(A[],subH+1,subAf)
		merge(A[],subAi,subH,subAf)
```

`Output: A[1,...,n] ordinato`

**Invarianti e corretteza mergeSort(A,subAi,subAf)**

* per induzione su `subAf-subAi` (sottoarray di **A**)
 1. se 0 al più un elemento -> OK
 2. se `subAf-subAi`>0 -> `subH-subAi`,`subAf-subH+1 < subAf-subAi`
* per ipotesi induttiva
 1. stato iniziale disordinato
 2. ordinamento su **L** `mergesort(A,subAi,sub)`
 3. ordinamento su **R** `mergesort(A,subH+1,subAf)`
 4. per correttezza di merge -> dopo merge `A[subAi..subAf]` ordinato
		
`Input: A[subAi...subH...subAf]`

```python
merge(A[],subAi,subH,subAf)
	n1 = subH-subAi+1 		  # +1 perché contiamo da 1
	n2 = subAf-subH
	for i=1 to n1
		L[i] = A[subAi+i-1]
		for z=1 to n2
			R[z] = A[subAi+z]
			L[n1+1] = R[n2+1] = "infinito"
			i = z = 1
			for k=subAi to subAf
				if(L[i]<= R[z]) # se uguali prendo prima quello a sinistra
					A[k] = L[i]
					i++
				else # se L[i] > R[z]
					A[k] = R[z]
					z++
```

`Output: A[subAi,...,subAf] ordinato`
	
**Invarianti e corretteza merge(A,subAi,subH,subAf)**
	

* **L** da 1 a **n1** (infinito) `A[subAi..subH]`
* **R** da 1 a **n2** (infinito) `A[subH+1..subAf]`
		
 1. `A[subAi..k-1]` ordinata
 2. contiene `L[1..i-1]` e `R[1..z-1]`
 3. `A[subAi..k-1] <= L[i..n1],R[z..n2]`
		
	
**Costi**

- Avg: 
- Worst: A ordinato in modo inverso ->
- Best: A ordinato ->

![Alt Animated GIF of the merge sort](https://upload.wikimedia.org/wikipedia/commons/c/c5/Merge_sort_animation2.gif)
![Alt Graphical example of the merge sort](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif)

[Wikipedia Link](https://en.wikipedia.org/wiki/Merge_sort "Merge Sort link to Wikipedia")


# Credits

* [Vashy](https://github.com/Vashy "Link to Vashy's GitHub profile")'s [ASD-Notes](https://github.com/Vashy/ASD-Notes "Link to ASD-Notes") repository
* [Wikipedia](https://en.wikipedia.org "Wikipedia")
