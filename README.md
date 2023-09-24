# mathmini-brew
Sample math library containing add and sub functions

# Installation
```bash
brew tap jameelkaisar/tap
brew install mathmini
```

# Usage
```bash
mathmini add 10 5
mathmini sub 10 5
```

```c
#include <stdio.h>
#include <mathmini.h>

int main() {
    printf("%d\n", add(10, 5));
    printf("%d\n", sub(10, 5));
    return 0;
}
```
- Compile with `-lmathmini` flag

# Release and Publish
1. Commit changes
2. Run `git tag v1.0.0`
3. Run `git push origin v1.0.0`
