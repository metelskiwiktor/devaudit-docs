# Pule wątków i ExecutorService

Pule wątków pozwalają zarządzać wieloma zadaniami przy ograniczonej liczbie wątków.

## Przykład

```java
ExecutorService executor = Executors.newFixedThreadPool(4);
executor.submit(() -> doWork());
```

## Zalety:
- Lepsze wykorzystanie zasobów
- Ograniczenie kosztu tworzenia nowych wątków