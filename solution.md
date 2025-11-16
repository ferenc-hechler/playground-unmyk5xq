# Python Solution

```
def solution(N:int):
    result = 0
    for digit in str(N):
        result = result + int(digit)
    return result
```

# Java Solution

```
  public static int loesung(int N) {
    int result = 0;
    String numString = Integer.toString(N);
    for (int i=0; i<numString.length(); i++) {
        result += Integer.parseInt(numString.substring(i,i+1));
    }
    return result;
  }
```

# C Solution

```
static int loesung(unsigned N) {
    unsigned result = 0;
    unsigned val = N;
    while (val > 0) {
        result += val % 10;
        val /= 10;
    }
    // TODO end remove

   return result;
}
```
