**Podstawy synchronizacji**

W środowisku wielowątkowym kilka wątków może próbować jednocześnie uzyskać dostęp do tych samych zasobów — na przykład zmiennych, plików lub baz danych. Bez odpowiedniego mechanizmu synchronizacji może to prowadzić do błędów, takich jak zakleszczenia lub niespójność danych.

**Problem współbieżnego dostępu:**

Wyobraź sobie dwa wątki jednocześnie modyfikujące zmienną `saldo`. Bez synchronizacji jeden z wątków może nadpisać zmiany drugiego — tzw. warunek wyścigu (race condition).

**Rozwiązanie: Synchronizacja**

W językach takich jak Java, słowo kluczowe `synchronized` umożliwia sekwencyjny dostęp do sekcji kodu, tak by tylko jeden wątek mógł ją wykonać w danym momencie.

**Przykład w Javie:**
```java
public synchronized void wypłać(int kwota) {
    if (saldo >= kwota) {
        saldo -= kwota;
    }
}
```

**Monitor i lock:**

Każdy obiekt w Javie posiada tzw. monitor. `synchronized` sprawia, że wątek musi zdobyć "lock" na obiekcie, zanim wejdzie do bloku kodu.

**Podsumowanie:**

Synchronizacja jest niezbędna, aby zapewnić poprawność działania programu wielowątkowego. Należy jednak jej używać ostrożnie, aby unikać zatorów (deadlock) i nadmiernego spowalniania programu.
