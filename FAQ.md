# Dlaczego pisaliśmy `psd[0]` w komendzie `plt.plot(psd[0])`?

`psd` to macierz numpy (*numpy array*), która ma dwa wymiary reprezentujące: 1) kanały; 2) częstotliwości.
`psd` dostajemy zawsze dwu-wymiarowe nawet gdy prosimy funkcję `psd_welch` o jeden kanał.
Gdy mamy dwu-wymiarową macierz np.:
```python
A = np.arange(12).reshape((3, 4))
```
```
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
```

i adresujemy jeden wiersz (np. drugi, czyli o indeksie 1 tzn. `A[1]`) to nie potrzebujemy już reprezentować wymiaru wierszy, bo wybraliśmy tylko jeden wiersz, można więc pominąć ten wymiar, co też numpy automatycznie robi:
```python
A[1]
```
```
array([4, 5, 6, 7])
```
dostajemy numpy array o jednym wymiarze. Możesz zresztą sprawdzić:
```python
print(A.shape)
print(A[1].shape)
```
```
(3, 4)
(4,)
```
Logika tego gubienia wymiarów jest podsumowując taka:
> Kiedy mamy salę kinową z ośmioma rzędami, a w każdym rzędzie mamy po dziesięć krzeseł, to warto na biletach opisywać miejsce numerem rzędu i krzesła. Jeżeli jednak zrobimy w sali kinowej przemeblowanie i zostawiamy tylko jeden rząd krzeseł - nie ma już potrzeby na bilecie informować gości o numerze rzędu - jest tylko jeden rząd, więc wystarczy im numer miejsca.

Także `psd[0]` robimy w podobny sposób - aby 'porzucić' wymiar kanałów (wybieramy jeden kanał, pierwszy, bo indeks jest zero) i zostawić tylko częstotliowości.  
Ale w jakim celu to robimy?
Otóż matplotlib gdy dostaje dwu-wymiarowe numpy arrays do narysowania domyślnie rysuje każdą kolumnę jako oddzielną linię, co w przypadku macierzy o wymiarach (jeden kanał, kilkaset próbek) dałoby bezsensowny obraz  (każda częstotliwość jako oddzielna jedno-punktowa linia) - dlatego porzucamy wymiar kanałów (nie daje dodatkowych informacji, bo mamy tylko jeden kanał, a przeszkadza w wyświetlaniu).
