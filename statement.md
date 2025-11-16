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
#include <stdlib.h>

static int loesung(unsigned N) {
    /* ----------------------------------- */
    /* - TODO: FÜGE DEINEN CODE HIER EIN - */
    /* ----------------------------------- */
    unsigned result = N;

    // TODO begin remove
    result = 0;
    unsigned val = N;
    while (val > 0) {
        result += val % 10;
        val /= 10;
    }
    // TODO end remove


    return result;
}


/* ------------------------------------------------------ */
/* ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- */
/* ------------------------------------------------------ */

int main(void) {
    struct test {
        unsigned input;
        unsigned check;
    };
    struct test tests[] = {
        {12, 762299093}, {56, 1049489039}, {2025, 909320628},
        {8, 462648444}, {0, 1804289383}, {9999, 687175592}, {17112025, 796206383}
    };
    for (int i = 0; i < sizeof(tests) / sizeof(struct test); i++) {
         unsigned N = tests[i].input;
         unsigned check = tests[i].check;
         unsigned result = loesung(N);
         srand(tests[i].input + result);
         unsigned chk = rand();
         if (chk == check) {
             printf("RICHTIG: Die Quersumme von %u ist %u\n", N, result);
         } else {
             // printf("FALSCH: Die Quersumme von %u ist nicht %u (%u)\n", N, result, chk);
             printf("FALSCH: Die Quersumme von %u ist nicht %u (%u)\n", N, result, chk);
             return 1;
         }
    }
    return 0;
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


## Node.JS (Work in Progress)

```javascript runnable
console.log('Hello World!');
```


## C# (Work in Progress)

```C# runnable
// { autofold
using System;

class Hello 
{
    static void Main() 
    {
// }

Console.WriteLine("Hello World!");

// { autofold
    }
}
// }
```

## GO (Work in Progress)

```go runnable
package main

import "fmt"

func main() {
    fmt.Println("Hello World!")
}
```


## BASH (Work in Progress)


```bash runnable
echo "Hello World!"
```

## VB.NET (Work in Progress)

```vb.net runnable
Imports System

Public Module modmain
   Sub Main()
     Console.WriteLine ("Hello World!")
   End Sub
End Module
```

## Kotlin (Work in Progress)


```kotlin runnable
fun main(args: Array<String>) {
    println("Hello, World!")
}
```

