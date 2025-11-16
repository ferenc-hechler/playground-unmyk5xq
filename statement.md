# Programmieraufgabe Quersumme

Für eine gegebene Zahl `N` berechne die **Quersumme**.

Die Quersumme wird berechnet, indem alle Ziffern der Zahl aufaddiert werden.  
Zum Beispiel hat `2025` die Quersumme `9`, da `2+0+2+5 = 9` ist.

Implementiere die Methode `loesung(N)` im Code und klicke anschliessend den "Run" Button unten um die Testfälle laufen zu lassen.

**Bedingungen:**  
0 ≤ N ≤ 1000000000


Suche unten die dür dich passende Programmiersprache (Python/JAVA) aus:

## PYTHON


```python runnable

def loesung(N:int):
    # ----------------------------------- #
    # - TODO: FÜGE DEINEN CODE HIER EIN - #
    # ----------------------------------- #
    result = N

    return result


# ------------------------------------------------------ #
# ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- #
# ------------------------------------------------------ #

INPUTS = [12, 56, 2025, 8, 0, 9999, 17112025]
CHECKS = [1656302624, 3832185857, 3205138698, 2846111786, 3158815156, 3540719418, 3071405752]

import sys
import hashlib
from datetime import datetime, timedelta

for N, check in zip(INPUTS, CHECKS):
    result = loesung(N)
    chk = hashlib.md5(f"{N}{result}".encode()).digest()
    chk = (((chk[3]<<8)+chk[2]<<8)+chk[1]<<8)+chk[0]
    #print(chk)
    if chk == check:
        print(f'RICHTIG: Die Quersumme von {N} ist {result}')
    else:
        print(f'FALSCH: Die Quersumme von {N} ist nicht {result}', file=sys.stderr)
        sys.exit(1)
        
print("------------------------------------------------------------")
print(f"ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um {datetime.now()+ timedelta(hours=1)}")

```

## JAVA

```java runnable
import java.util.Date;
public class Main {
  public static int loesung(int N) {
    /* ----------------------------------- */
    /* - TODO: FÜGE DEINEN CODE HIER EIN - */
    /* ----------------------------------- */
    int result = N;


    return result;
  }


  /* ------------------------------------------------------ */
  /* ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- */
  /* ------------------------------------------------------ */

  public static void main(String[] args) {

    int[] INPUTS = {12, 56, 2025, 8, 0, 9999, 17112025};
    int[] CHECKS = {48690, 1632385, 47655768, 1792, 1536, 1686256803, -151278289};

    for (int i=0; i<INPUTS.length; i++) {
        int N = INPUTS[i];
        int check = CHECKS[i];
        int result = loesung(N);
        int chk = (Integer.toString(N)+Integer.toString(result)).hashCode();
        // System.out.println(chk);
        if (chk == check) {
            System.out.println("RICHTIG: Die Quersumme von "+N+" ist "+result);
        }
        else {
            System.err.println("FALSCH: Die Quersumme von "+N+" ist nicht "+result);
            System.exit(1);
        }    
    }
    System.out.println("------------------------------------------------------------");
    System.out.println("ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um "+new Date().toString());
  }
}
```

## C (Work in Progress)

```C runnable
#include <stdio.h>

int main() {
	printf("Hello World!");
}

```

## C++ (Work in Progress)

```C++ runnable
#include <iostream>

using namespace std;

int main() 
{
    cout << "Hello, World!";
    return 0;
}
```

