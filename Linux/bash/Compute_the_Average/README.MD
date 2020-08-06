# Problem

![problem](/Linux/bash/Compute_the_Average/problem.png)

## Solution

```bash
read n
total=0

# Add number to total in each loop
for ((i = 0; i < $n ; i++))
do
    read num
    total=$(( $total + $num ))
done

echo "$total / $n" | bc -l | xargs printf "%.3f"
```
