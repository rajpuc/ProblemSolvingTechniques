# ProblemSolvingTechniques
# Day 1:
### GCD: Greatest Common divisor. Question: 15,9 er GCD ber koro?
- ### GCD holo amn akta number : j shokol shonkha diye 15,9 k divide korle remainder 0 hoi shei shokol number er moddhe boro number ta k bole GCD. Jemon 15,9 er GCD 3. For example 106 & 16 er gcd 2.
![](./images/1.png)
- ### You can solve GCD using Recursion
```javascript
function gcd(a,b){
    if(a === 0) reuturn b; // ata k recursion er khetre "base case" bole
    return gcd(b % a, a) // ata k "recursive case" bole.
    // Steps for gcd(15, 9)
    /*
    Iteration 1:
        a = 15, b = 9
        b % a = 9
        Recursive call: gcd(9, 15)

    Iteration 2:
        a = 9, b = 15
        b % a = 6
        Recursive call: gcd(6, 9)

    Iteration 3:
        a = 6, b = 9
        b % a = 3
        Recursive call: gcd(3, 6)

    Iteration 4:
        a = 3, b = 6
        b % a = 0
        Recursive call: gcd(0, 3)

    Base Case Reached:
        Result = 3
    */


}
```
### LCM: least common multiple. Question: 15,9 er LCM ber koro?
- ### LCM: J shokol shonkha k amra 15,9 ai 2ta number diyey devide korer por remainder 0 ashbe, she shokol shokhar moddhe sobceye choto shonkha ta k LCM bole.
- ### 15,9 er LCM hocce 45.
- ### `LCM(a,b)×GCD(a,b)=a×b`
- ### hence,   `LCM(a,b) = (aXb) / GCD(a,b)`



# Day 2:
problem link: https://www.naukri.com/code360/problems/sum-of-all-divisors_8360720
### Harmonic Lemma: Efficient Summation

### Key Insight (Harmonic Lemma)
The value of 〈 n / i 〉 (the floor of n divided by i) does not change very often. This allows us to group ranges of values where 〈 n / i 〉 is constant, making the summation more efficient.

### Example with n = 10:

Let’s calculate 〈 10 / i 〉 for i from 1 to 10:

| i   | 〈 10 / i 〉 |
|------|--------------|
| 1    | 10           |
| 2    | 5            |
| 3    | 3            |
| 4    | 2            |
| 5    | 2            |
| 6    | 2            |
| 7    | 1            |
| 8    | 1            |
| 9    | 1            |
| 10   | 1            |

### Observations:
1. **Distinct Values of 〈 n / i 〉:**
   - The values are: [10, 5, 3, 2, 1].
   - There are only 5 distinct values of 〈 n / i 〉, even though i ranges from 1 to 10.

2. **Constant Ranges:**
   - For i = 1: 〈 10 / 1 〉 = 10.
   - For i = 2: 〈 10 / 2 〉 = 5.
   - For i = 3: 〈 10 / 3 〉 = 3.
   - For i = 4 to i = 6: 〈 10 / i 〉 = 2.
   - For i = 7 to i = 10: 〈 10 / i 〉 = 1.

3. **Efficiency Insight:**
   - 〈 n / i 〉 is constant over certain ranges of i.
   - Example: For i = 4 to i = 6, 〈 10 / i 〉 remains 2.

4. **Number of Distinct Values:**
   - The number of distinct values of 〈 n / i 〉 is small: at most **2 √ n**.

---

### Implication for Efficient Calculation
By identifying ranges where 〈 n / i 〉 is constant, we can:
1. **Reduce Redundant Calculations:** Sum contributions for all i in a range at once.
2. **Time Complexity:** Achieve \(O(\sqrt{n})\) efficiency instead of \(O(n)\).

---
![](./images/2.png)







