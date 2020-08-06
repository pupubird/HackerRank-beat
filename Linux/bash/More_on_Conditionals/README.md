# Problem

![problem](/Linux/bash/More_on_Conditionals/problem.png)

## Solution

```bash
read x
read y
read z

if [[ $x == $y && $y == $z ]]
then
    echo "EQUILATERAL"
elif [[ $x == $y || $y == $z || $x == $z ]]
then
    echo "ISOSCELES"
else
    echo "SCALENE"
fi
```

Discovered a better solution:
[https://www.hackerrank.com/challenges/bash-tutorials---more-on-conditionals/forum/comments/299738](https://www.hackerrank.com/challenges/bash-tutorials---more-on-conditionals/forum/comments/299738) by 
swdotca

```bash
# Solution based on counting number of unique values

c=$(cat | tr ' ' "\n" | sort -n -u | wc -l)

[ $c -eq 1 ] && echo EQUILATERAL
[ $c -eq 2 ] && echo ISOSCELES
[ $c -eq 3 ] && echo SCALENE
```

Explaination:

The solution is based on sorting and counting distinct values using wc i.e word count. So for instance, if you have input as 2,2,1 the value of variable c would be 2 since it counts both these 2's as a single 2 alongwith 1. So logically your input 2,2,1 becomes 2,1 and word count gives you a count of distinct lines and thus variable c holds a value of 2 and thus its isoceles. And if the input is 3,3,3 then all these 3's are counted once and then the wc command would return the value of variable c as 1 and thus it would be equilateral.

--- from milind270989, [https://www.hackerrank.com/challenges/bash-tutorials---more-on-conditionals/forum/comments/399517](https://www.hackerrank.com/challenges/bash-tutorials---more-on-conditionals/forum/comments/399517)
