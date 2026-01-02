# Symulacja roju autonomicznych dronów
## Systemy Operacyjne

### 1. Cel projektu
Celem projektu jest zaimplementowanie symulacji roju autonomicznych dronów.  
W projekcie zaadresowane powinny być problemy poprawnego obsługiwania procesów, komunikacji pomiędzy nimi, a także zarządzania zasobami.  
Wykorzystywane będą między innymi sygnały, semafory i inne mechanizmy systemowe.

---

### 2. Opis systemu
W symulacji występują trzy główne elementy: **drony**, **operator** oraz **dowódca systemu**.

**Drony** reprezentują autonomiczne jednostki, które naprzemiennie wykonują lot i wracają do bazy na ładowanie. Każdy dron ma indywidualne parametry, takie jak czas ładowania, maksymalny czas lotu oraz liczba cykli, po których zostaje wycofany z eksploatacji.  
Dron musi wrócić do bazy zanim bateria spadnie do 0%, w przeciwnym razie ulega zniszczeniu. Dowódca może też wysłać do drona sygnał wykonania ataku samobójczego, jeśli ten posiada co najmniej 20% baterii.

**Operator** zarządza bazą, która ma ograniczoną pojemność i dwa wejścia mogące działać tylko w jednym kierunku w danym momencie. Operator kontroluje wchodzenie i wychodzenie dronów, dba o liczebność roju oraz reaguje na sygnały dowódcy.

**Dowódca systemu** może wpływać na pracę całego roju, zwiększając lub zmniejszając maksymalną liczbę dronów, a także wysyłając sygnały bezpośrednio do wybranej jednostki.

---

### 3. Proponowane testy
Do sprawdzenia poprawności działania symulacji planowane są proste scenariusze testowe:

1. **Test podstawowy** – kilka dronów, brak sygnałów od dowódcy.  
   Sprawdzane będzie, czy drony prawidłowo latają, ładują się i są utylizowane po określonej liczbie cykli.

2. **Mała pojemność bazy** – ustawienie niskiego limitu `P`.  
   Test sprawdzi, jak system zachowuje się przy dużym obciążeniu tuneli oraz czy drony poprawnie czekają na wejście.

3. **Reakcja na sygnały dowódcy** – wysyłanie sygnałów zwiększających lub zmniejszających liczbę dronów oraz poleceń ataku.  
   Pozwoli to zweryfikować poprawność komunikacji i obsługę sygnałów podczas działania aplikacji.

4. **Większe obciążenie** – uruchomienie większej liczby dronów.  
   Test sprawdzi stabilność systemu, poprawne działanie semaforów oraz ogólną wydajność.


---
