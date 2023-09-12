# Reto número 3 repo
### Fecha:  30-08-2023
**1.** Algoritmo para obtener los números primos hasta un número n
* Primero realicé el diagrama de flujo para facilitar el proceso de creación del pseudocódigo:
```mermaid
flowchart TB;
    A([START])--> B[/"n=0 ; Divisors=[] ; i=0 ; j=0"/]
    B --> C[Insert number n]
    C --> W[/n/]
    W ---> D{n>1}
    D -- NO --> E[Insert an integer number > 1]
    E --> C
    D -- YES --> F{{For i=1 in range n}}
    F --> J([i])
    J --> G{{For j=2 in range i**0.5}}
    G --> K([j])
    K --> H{i % j == 0}
    H -- TRUE --> I["Divisors=[j]"]
    H -- FALSE --> G
    I --> L{j < i**0.5}
    L -- TRUE --> K
    L -- FALSE --> M{If the length of: Divisors == 0}
    M -- FALSE --> J
    M -- TRUE --> N[/Divisors/]
    N --> O((END))
```
* Despues, teniendo en cuenta el diagrama de flujo escribí el pseudocodigo de la siguiente manera:
```pseudocode
Algoritmo Numerosprimos
	n=0
	Divisors=[]
	i=0
	j=0
	Escribir Insert number n
	Leer n
	Si n>1 Entonces
		Para i<-1 Hasta n Hacer
			Para j<-2 Hasta i^0.5 Hacer
				Si i%j==0 Entonces
					Divisors=[j]
					Si j<i^0.5 Entonces
						Si length of Divisors==0 Entonces
							Leer Divisors
						Fin Si
					Fin Si
				Fin Si
			Fin Para
		Fin Para
	SiNo
		Escribir Insert an integer number > 1
	Fin Si
FinAlgoritmo
FinAlgoritmo
```
**2.** Algoritmo para obtener la raiz cuadrada de un número n
* Primero realicé el diagrama de flujo para facilitar el proceso de creación del pseudocódigo, me basé en el método de Newton Raphson:
```mermaid
flowchart TB;
    A([START])--> B["X=0 ; Xnew=0; n=0"]
    B --> C["Insert number X"]
    C --> D[/n/]
    D --> E{"n > 0"}
    E -->|NO| F["Insert an integer number > 0"]
    F ----> C
    E -->|YES| H["X=n/2"]
    H --> Z([X])
    Z --> J["Xnew=(0.5)*((X)+(n/X))"]
    J --> I{"X-Xnew < 0.00001"}
    I -- FALSE --> K["X=Xnew"]
    K --> Z
    I -- TRUE --> M["√n is:"]
    M --> N[/Xnew/]
    N --> O((END))
```
Referencia: http://ojs.urepublicana.edu.co/index.php/ingenieria/article/view/347/314

* Despues, teniendo en cuenta el diagrama de flujo escribí el pseudocodigo de la siguiente manera:
```pseudocode
Algoritmo RaizCuadrada
	X=0
	Xnew=0
	n=0
	Escribir Insert number n
	Leer n
	Si n>0 Entonces
		X=n/2
		Leer X
		Xnew=(0.5)*((X)+(n/X))
		Si X-Xnew<0.00001 Entonces
			Escribir "n^0.5 is:"
			Leer Xnew
		SiNo
			X=Xnew
		Fin Si
	SiNo
		Escribir Insert an integer number > 0
	Fin Si
FinAlgoritmo
```
