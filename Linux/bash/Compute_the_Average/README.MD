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

Alternative solution:

[https://www.hackerrank.com/challenges/bash-tutorials---compute-the-average/forum/comments/114630](https://www.hackerrank.com/challenges/bash-tutorials---compute-the-average/forum/comments/114630)
by pranitbose_15

```bash
read n
arr=($(cat)) 
arr=${arr[*]}
printf "%.3f" $(echo $((${arr// /+}))/$n | bc -l)
```

Explaination:

[https://www.hackerrank.com/challenges/bash-tutorials---compute-the-average/forum/comments/133151](https://www.hackerrank.com/challenges/bash-tutorials---compute-the-average/forum/comments/133151)