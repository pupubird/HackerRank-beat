# Problem

![problem](/Linux/bash/Arithmetic_Operations/problem.png)

## Solution

```bash
read exp
echo $exp | bc -l | xargs printf "%.3f"
```

Note the reason why we need to pipe it to `printf` is because `bc` does not round the floating points, rather, it chopped off the floating points. Hence, we are using `printf` to round it.
