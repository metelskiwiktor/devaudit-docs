**Komunikacja między wątkami**

Wątki w jednym programie często muszą ze sobą współpracować. Komunikacja między wątkami pozwala na wymianę informacji i koordynację ich działań — np. czekanie na wynik działania innego wątku.

**Problemy bez komunikacji:**

Jeśli jeden wątek produkuje dane, a drugi je przetwarza, to bez synchronizacji mogą pojawić się sytuacje, w których konsument działa za szybko lub za wolno — tzw. problem producenta i konsumenta.

**Rozwiązanie: wait/notify**

Java oferuje mechanizmy `wait()`, `notify()`, `notifyAll()` do zarządzania współdzielonymi zasobami:

```java
synchronized (sharedObject) {
    while (!warunek) {
        sharedObject.wait();
    }
    // przetwarzanie danych
    sharedObject.notify();
}
```

- `wait()` — wątek czeka, aż ktoś go powiadomi
- `notify()` — budzi jeden oczekujący wątek
- `notifyAll()` — budzi wszystkie czekające wątki

**Alternatywy nowoczesne:**

Od Javy 5 dostępne są klasy wyższego poziomu, takie jak `BlockingQueue`, `CountDownLatch`, `Semaphore`, które upraszczają komunikację i synchronizację.

**Podsumowanie:**

Efektywna komunikacja między wątkami to klucz do wydajnych i bezpiecznych aplikacji wielowątkowych. Warto korzystać z nowoczesnych narzędzi i unikać ręcznego zarządzania synchronizacją, jeśli to możliwe.
