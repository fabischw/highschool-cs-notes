# --Translated [sorting.md](./sorting.md) by ChatGPT--



**Insertion Sort**
```python
def insertion_sort(L):
    for i in range(len(L)):
        for j in range(0, i):
            if L[j] > L[i]:
                # tausche L[j] und L[i]
                L[j], L[i] = L[i], L[j]
    return L

```

- Platzkomplexität: O(1)
- Zeitkomplexität: O(n^2) im schlechtesten und durchschnittlichen Fall, O(n) im besten Fall
- Video-Link: https://www.youtube.com/watch?v=JMRU2nh6bfs

<details>
<summary>Erklärung</summary>

1.  Die Eingabe ist eine Liste von Elementen, L.
2.  Die äußere Schleife wird len(L) Mal durchlaufen, da in jeder Iteration ein Element in den sortierten Teil der Liste eingefügt wird.
3.  In jeder Iteration ist die Variable i der Index des Elements, das in den sortierten Teil der Liste eingefügt werden soll.
4.  Die innere Schleife läuft von 0 bis i-1, da dies die Indizes der Elemente im sortierten Teil der Liste sind, die potenziell größer als L[i] sind.
5.  Wenn das Element an Index j größer als das Element an Index i ist, werden die Elemente vertauscht, sodass L[i] an der richtigen Position im sortierten Teil der Liste eingefügt wird.
7.  Nach Abschluss der inneren Schleife sind die ersten i+1 Elemente der Liste sortiert.
8.  Die sortierte Liste wird zurückgegeben.

</details>




**Selection Sort**
```python
def selection_sort(L):
    for i in range(len(L)):
        # finde Index des minimalen Elements im unsortierten Teil
        min_index = i
        for j in range(i+1, len(L)):
            if L[j] < L[min_index]:
                min_index = j
        # tausche minimales Element mit erstem Element des unsortierten Teils
        L[i], L[min_index] = L[min_index], L[i]
    return L
```

- Platzkomplexität: O(1)
- Zeitkomplexität: O(n^2) in allen Fällen
- Video-Link: https://www.youtube.com/watch?v=6S_mu-U0VTI
<details>
<summary>Erklärung</summary>

1. Die Eingabe ist eine Liste von Elementen, L.
2. Die äußere Schleife wird len(L) Mal durchlaufen, da in jeder Iteration das kleinste Element aus dem unsortierten Teil der Liste ausgewählt und an den Anfang gestellt wird.
3. In jeder Iteration wird die Variable min_index auf i gesetzt, der Index des ersten Elements im unsortierten Teil der Liste.
4. Die innere Schleife läuft von i+1 bis len(L), da die ersten i Elemente bereits sortiert sind.
5. Wenn das Element an Index j kleiner als das Element an Index min_index ist, wird der Index von min_index auf j gesetzt.
6. Nach Abschluss der inneren Schleife befindet sich das minimale Element im unsortierten Teil der Liste an Index min_index.
7. Das minimale Element wird mit dem ersten Element im unsortierten Teil der Liste an Index i vertauscht.
8. Die sortierte Liste wird zurückgegeben.

</details>




**Bubble Sort**
```python
def bubble_sort(L):
    n = len(L)
    swapped = False # Flag, um zu überprüfen, ob ein Tausch stattgefunden hat
    for i in range(n-1):
        for j in range(0, n-i-1):
            if L[j] > L[j+1]:
                swapped = True # Ein Tausch hat stattgefunden
                # Tausche benachbarte Elemente, wenn sie nicht in der richtigen Reihenfolge sind
                L[j], L[j+1] = L[j+1],L[j]
        if not swapped:
            break # Kein Tausch bedeutet, dass die Liste bereits sortiert ist
    return L

```

- Platzkomplexität: O(1)
- Zeitkomplexität: O(n^2) im schlechtesten und durchschnittlichen Fall, O(n) im besten Fall
- Video-Link: https://www.youtube.com/watch?v=ARZLBeagiJ4

<details>
<summary>Erklärung</summary>

1. Die Eingabe ist eine Liste von Elementen, L.
2. Die Länge der Liste wird in der Variablen n gespeichert.
3. Ein Flag, swapped, wird auf False initialisiert.
4. Die äußere Schleife läuft n-1 Mal, da jeder Durchlauf das größte unsortierte Element ans Ende der Liste bringt.
5. Die innere Schleife läuft vom Anfang der Liste bis n-i-1, da die letzten i Elemente bereits sortiert sind.
6. Wenn das Element an der Stelle j größer ist als das Element an der Stelle j+1, werden die Elemente getauscht und swapped wird auf True gesetzt.
7. Nachdem die innere Schleife abgeschlossen ist, bedeutet ein unverändertes swapped, dass die Liste bereits sortiert ist und der Algorithmus frühzeitig beendet wird.
8. Die sortierte Liste wird zurückgegeben.

</details>




