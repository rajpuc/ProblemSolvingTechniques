## Day 4: Recursion
```cpp

#include<bits/stdc++.h>
using namespace std;

void func(int i, int n){
   
   // Base Condition.
   if(i<1) return;
   
   
   func(i-1,n);
   cout<<i<<endl;//This is called backtracking in recursion.

}

int main(){
  
  // Here, let’s take the value of n to be 4.
  int n = 4;
  func(n,n);
  return 0;

}
```

```cpp
//Sum of first N Natural Numbers
//Explanation: 1+2+3+4+5=15
//parameterized way
void func(i,sum)
{
   if(i<1)
   {
     print(sum);
     return;
   }

func(i-1,sum+i);

}

main()
{
   input(n);
   func(n,0);

}
// Functional way
int func(n)
{
   if(n == 0)
   {
     return 0;
   }

return n + func(n-1);

}

main()
{
   input(n);
   func(n);

}


```