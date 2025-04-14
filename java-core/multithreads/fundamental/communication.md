**Cykl życia wątku**

Wątek w programie przechodzi przez kilka charakterystycznych etapów — tzw. cykl życia wątku. Zrozumienie tych etapów jest kluczowe do prawidłowego zarządzania wykonywaniem zadań współbieżnych.

**1. Nowy (New)**  
Wątek zostaje utworzony, ale jeszcze nie został uruchomiony. Przykład: `Thread t = new Thread();`

**2. Gotowy (Runnable)**  
Po wywołaniu `start()`, wątek jest gotowy do wykonania i czeka na przydzielenie czasu procesora przez planistę (scheduler).

**3. Wykonywany (Running)**  
Wątek aktualnie się wykonuje. Może to być wykonywanie kodu w metodzie `run()`.

**4. Zablokowany / Oczekujący (Blocked / Waiting / Timed Waiting)**  
Wątek tymczasowo nie może się wykonywać, np. czeka na zakończenie operacji I/O lub zwolnienie zasobu.

**5. Zakończony (Terminated)**  
Wątek kończy działanie, gdy metoda `run()` dobiegnie końca lub zostanie przerwana.

**Przykład wizualny cyklu:**
```
New → Runnable → Running → (Waiting/Blocked) → Running → Terminated
```

**Ważne:**  
Nie należy próbować ponownie uruchamiać wątku po jego zakończeniu — wątek można uruchomić tylko raz.
