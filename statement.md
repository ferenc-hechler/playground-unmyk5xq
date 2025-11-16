# Programmieraufgabe Quersumme

Für eine gegebene Nummer `N` berechne die **Quersumme**.

The Quersumme wird berechnet, indem alle Ziffern der Zahl aufsumiert werden.
Zum Beispiel hat `2025` die Quersumme `9`, da `2+0+2+5 = 9` ist.

Implementiere die Methode loesung(N) im Code und klicke anschliessend den "Run" Button unten um die Testfälle laufen zu lassen.

**Einschränkungen:**
0 ≤ N ≤ 1000000000

```python runnable
def loesung(N:int):


    # ---------------------------- #
    # - TODO: ADD YOUR CODE HERE - #
    # ---------------------------- #
    result = N

    return result


# -------------------------------------------------- #
# ---------- DO NOT MODIFY THE CODE BELOW ---------- #
# -------------------------------------------------- #

INPUTS = [12, 56, 2025, 8, 0, 9999, 17112025]
CHECKS = [1656302624, 3832185857, 3205138698, 2846111786, 3158815156, 3540719418, 3071405752]

import sys
import hashlib
from datetime import datetime, timedelta

for N, check in zip(INPUTS, CHECKS):
    result = solution(N)
    chk = hashlib.md5(f"{N}{result}".encode()).digest()
    chk = (((chk[3]<<8)+chk[2]<<8)+chk[1]<<8)+chk[0]
    #print(chk)
    if chk == check:
        print(f'GOOD: Digital Root for {N} is {result}')
    else:
        print(f'FAIL: Digital Root for {N} is not {result}', file=sys.stderr)
        sys.exit(1)
        
print("------------------------------------------------------------")
print(f"SUCCESS: congratulations, you solved the riddle at {datetime.now()+ timedelta(hours=1)}")

```
