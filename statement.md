# Programmieraufgabe Quersumme Dezember 2025

Für eine gegebene Zahl `N` berechne die **Quersumme**.

Die Quersumme wird berechnet, indem alle Ziffern der Zahl aufaddiert werden.  
Zum Beispiel hat `2025` die Quersumme `9`, da `2+0+2+5 = 9` ist.

Implementiere die Methode `loesung(N)` im Code unten in der Programmiersprache Deiner Wahl (Python/Java/C) 
und klicke anschliessend den "Run" Button unter dem Code um die Testfälle laufen zu lassen.

**Bedingungen:**  
0 ≤ N ≤ 1000000000



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

## C

```C runnable
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
static int loesung(unsigned N) {
    /* ----------------------------------- */
    /* - TODO: FÜGE DEINEN CODE HIER EIN - */
    /* ----------------------------------- */
    unsigned result = N;

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
            // fprintf(stderr, "FALSCH: Die Quersumme von %u ist nicht %u (%u)\n", N, result, chk);
            fprintf(stderr, "FALSCH: Die Quersumme von %u ist nicht %u\n", N, result);
            return 1;
        }
    }
	time_t now = time(NULL);
	now += 60 * 60;
	struct tm *tm = localtime(&now);
	char buf[1024];
	strftime(buf, 1023, "------------------------------------------------------------\n"
		"ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um %a %b %d %H:%M:%S", tm);
	puts(buf);
    return 0;
}
```

## C++

```C++ runnable
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

using namespace std;

int loesung(unsigned int N) {
    /* ----------------------------------- */
    /* - TODO: FÜGE DEINEN CODE HIER EIN - */
    /* ----------------------------------- */
    int result = N;

    return result;
}

/* ------------------------------------------------------ */
/* ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- */
/* ------------------------------------------------------ */

int main() 
{
    struct Test {
        unsigned int input;
        unsigned int check;
    };
    
    Test tests[] = {
        {12, 762299093}, {56, 1049489039}, {2025, 909320628},
        {8, 462648444}, {0, 1804289383}, {9999, 687175592}, {17112025, 796206383}
    };
    
    for (int i = 0; i < 7; i++) {
        unsigned int N = tests[i].input;
        unsigned int check = tests[i].check;
        unsigned int result = loesung(N);
        srand(tests[i].input + result);
        unsigned int chk = rand();
        if (chk == check) {
            cout << "RICHTIG: Die Quersumme von " << N << " ist " << result << endl;
        } else {
            cerr << "FALSCH: Die Quersumme von " << N << " ist nicht " << result << endl;
            return 1;
        }
    }
    
    time_t now = time(NULL);
    now += 60 * 60;
    struct tm *tm = localtime(&now);
    char buf[1024];
    strftime(buf, 1023, "ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um %a %b %d %H:%M:%S", tm);
    cout << "------------------------------------------------------------" << endl;
    cout << buf << endl;
    
    return 0;
}
```


## Node.JS

```javascript runnable
function loesung(N) {
    // ----------------------------------- //
    // - TODO: FÜGE DEINEN CODE HIER EIN - //
    // ----------------------------------- //
    let result = N;

    return result;
}

// ------------------------------------------------------ //
// ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- //
// ------------------------------------------------------ //

const INPUTS = [12, 56, 2025, 8, 0, 9999, 17112025];
const CHECKS = [1656302624, -462781439, -1089828598, -1448855510, -1136152140, -754247878, -1223561544];

const crypto = require('crypto');

for (let i = 0; i < INPUTS.length; i++) {
    const N = INPUTS[i];
    const check = CHECKS[i];
    const result = loesung(N);
    
    const hash = crypto.createHash('md5').update(`${N}${result}`).digest();
    const chk = ((((hash[3] << 8) + hash[2]) << 8) + hash[1] << 8) + hash[0];
    
    if (chk === check) {
        console.log(`RICHTIG: Die Quersumme von ${N} ist ${result}`);
    } else {
        console.error(`FALSCH: Die Quersumme von ${N} ist nicht ${result}`);
        process.exit(1);
    }
}

console.log("------------------------------------------------------------");
const now = new Date();
now.setHours(now.getHours() + 1);
console.log(`ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um ${now}`);
```


## C# 

```C# runnable
using System;

class Program 
{
    static int Loesung(int N) 
    {
        /* ----------------------------------- */
        /* - TODO: FÜGE DEINEN CODE HIER EIN - */
        /* ----------------------------------- */
        int result = N;

        return result;
    }

    /* ------------------------------------------------------ */
    /* ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- */
    /* ------------------------------------------------------ */

    static void Main() 
    {
        int[] INPUTS = {12, 56, 2025, 8, 0, 9999, 17112025};
        int[] CHECKS = {289116474, 1449066918, 202469091, -1193887400, 1479163514, 1399327101, 1342042333};

        for (int i = 0; i < INPUTS.Length; i++) 
        {
            int N = INPUTS[i];
            int check = CHECKS[i];
            int result = Loesung(N);
            int chk = (N.ToString() + result.ToString()).GetHashCode();
            
            if (chk == check) 
            {
                Console.WriteLine($"RICHTIG: Die Quersumme von {N} ist {result}");
            }
            else 
            {
                Console.Error.WriteLine($"FALSCH: Die Quersumme von {N} ist nicht {result}");
                Environment.Exit(1);
            }    
        }
        
        Console.WriteLine("------------------------------------------------------------");
        Console.WriteLine($"ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um {DateTime.Now.AddHours(1)}");
    }
}
```

## GO

```go runnable
package main

import (
	"crypto/md5"
	"encoding/binary"
	"fmt"
	"os"
	"time"
)

func loesung(N int) int {
	// ----------------------------------- //
	// - TODO: FÜGE DEINEN CODE HIER EIN - //
	// ----------------------------------- //
	result := N

	return result
}

// ------------------------------------------------------ //
// ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- //
// ------------------------------------------------------ //

func main() {
	INPUTS := []int{12, 56, 2025, 8, 0, 9999, 17112025}
	CHECKS := []uint32{1656302624, 3832185857, 3205138698, 2846111786, 3158815156, 3540719418, 3071405752}

	for i, N := range INPUTS {
		check := CHECKS[i]
		result := loesung(N)
		
		hash := md5.Sum([]byte(fmt.Sprintf("%d%d", N, result)))
		chk := binary.LittleEndian.Uint32(hash[:4])
		
		if chk == check {
			fmt.Printf("RICHTIG: Die Quersumme von %d ist %d\n", N, result)
		} else {
			fmt.Fprintf(os.Stderr, "FALSCH: Die Quersumme von %d ist nicht %d\n", N, result)
			os.Exit(1)
		}
	}
	
	fmt.Println("------------------------------------------------------------")
	now := time.Now().Add(time.Hour)
	fmt.Printf("ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um %s\n", now.Format(time.RFC1123))
}
```


## BASH

```bash runnable
function loesung {
	N=$1
	###################################
	# TODO: FÜGE DEINEN CODE HIER EIN #
	###################################
	result=$N

	echo $result
}

######################################################
########## AB HIER DEN CODE NICHT VERÄNDERN ##########
######################################################

function main {
	local INPUTS=(12 56 2025 8 0 9999 17112025)
	local CHECKS=(52696 113217 74532 148306 64833 67628 30678)
	local i=0
	while test $i -lt ${#INPUTS[@]}; do
		local N=${INPUTS[$i]}
		local check=${CHECKS[$i]}
		local result="$(loesung $N)"
		local chk=`echo $result:$N | md5sum | sed 's/-//'`
		chk=$((16#$chk))
		((chk=(chk>>32)+(chk&((1<<32)-1))))
		((chk=(chk>>16)+(chk&((1<<16)-1))))
		if test $chk = $check; then
			echo "RICHTIG: Die Quersumme von $N ist $result"
		else
			echo "FALSCH: Die Quersumme von $N ist nicht $result" >&2
			exit 1
		fi
		((i++))
	done
	sec=`date +%s`
	((sec+=60*60))
	echo ------------------------------------------------------------
	echo -n 'ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um '
	date --date=@$sec '+%a %b %d %H:%M:%S'
}

main
```

## VB.NET

```vb.net runnable
Imports System

Public Module Program
    Function Loesung(N As Integer) As Integer
        ' ----------------------------------- '
        ' - TODO: FÜGE DEINEN CODE HIER EIN - '
        ' ----------------------------------- '
        Dim result As Integer = N

        Return result
    End Function

    ' ------------------------------------------------------ '
    ' ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- '
    ' ------------------------------------------------------ '

    Sub Main()
        Dim INPUTS() As Integer = {12, 56, 2025, 8, 0, 9999, 17112025}
        Dim CHECKS() As Integer = {289116474, 1449066918, 202469091, -1193887400, 1479163514, 1399327101, 1342042333}

        For i As Integer = 0 To INPUTS.Length - 1
            Dim N As Integer = INPUTS(i)
            Dim check As Integer = CHECKS(i)
            Dim result As Integer = Loesung(N)
            Dim chk As Integer = (N.ToString() + result.ToString()).GetHashCode()
            
            If chk = check Then
                Console.WriteLine("RICHTIG: Die Quersumme von "+N.ToString()+" ist "+result.ToString())
            Else
                Console.Error.WriteLine("FALSCH: Die Quersumme von "+N.ToString()+" ist nicht "+result.ToString())
                Environment.Exit(1)
            End If
        Next
        
        Console.WriteLine("------------------------------------------------------------")
        Console.WriteLine("ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um "+DateTime.Now.AddHours(1).ToString())
    End Sub
End Module
```

## Kotlin


```kotlin runnable
import java.util.Date
import java.security.MessageDigest

fun loesung(N: Int): Int {
    // ----------------------------------- //
    // - TODO: FÜGE DEINEN CODE HIER EIN - //
    // ----------------------------------- //
    var result = N

    return result
}

// ------------------------------------------------------ //
// ---------- AB HIER DEN CODE NICHT VERÄNDERN ---------- //
// ------------------------------------------------------ //

fun main(args: Array<String>) {
    val INPUTS = listOf(12, 56, 2025, 8, 0, 9999, 17112025)
    val CHECKS = listOf(1656302624L, 3832185857L, 3205138698L, 2846111786L, 3158815156L, 3540719418L, 3071405752L)
    
    for (i in INPUTS.indices) {
        val N = INPUTS[i]
        val check = CHECKS[i]
        val result = loesung(N)
        
        val md = MessageDigest.getInstance("MD5")
        val hash = md.digest("$N$result".toByteArray())
        val chk = (((hash[3].toLong() and 0xFF shl 8) + (hash[2].toLong() and 0xFF) shl 8) + (hash[1].toLong() and 0xFF) shl 8) + (hash[0].toLong() and 0xFF)
        
        if (chk == check) {
            println("RICHTIG: Die Quersumme von $N ist $result")
        } else {
            System.err.println("FALSCH: Die Quersumme von $N ist nicht $result")
            System.exit(1)
        }
    }
    
    println("------------------------------------------------------------")
    println("ERFOLG: Gratulation, Du hast die Aufgabe erfolgreich abgeschlossen um ${Date(System.currentTimeMillis() + 3600000)}")
}
```
