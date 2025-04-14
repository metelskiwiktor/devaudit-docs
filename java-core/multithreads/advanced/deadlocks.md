# Zjawisko zakleszczenia (Deadlocks)

Deadlock występuje, gdy dwa lub więcej wątków czekają wzajemnie na zasoby, które nigdy nie zostaną zwolnione.

## Przykład kodu

```java
synchronized (A) {
  synchronized (B) {
    // kod
  }
}
```

## Sposoby unikania:
- Unikanie zagnieżdżonych blokad
- Ustalony porządek pozyskiwania zasobów
