## Day 7: All other kind of patterns in Recursion
### Printing subsequences whose sum is k
```cpp
void f(int ind, vector<int> &ds, int s, int sum, int arr[],int n){
  if(ind == n){
    if(s == sum){
      for(auto it:ds) cout<<it<<" ";
      cout<<endl;
    }
    return;
  }
  ds.push_back(arr[ind]);
  s+= arr[ind];
  f(ind+1,ds,s,sum,arr,n);
  s-= arr[ind];
  ds.pop_back();
  f(ind+1,ds,s,sum,arr,n);
}

int main(){
  int arr[]={1,2,1};
  int n  = 3;
  int sum =2;
  vector<int> ds;
  f(0, ds, 0, sum, arr, n);
  return 0;
}
```
### If i modify the question: Print any one subsequence whose sum is sum(given to u);
```cpp
// You can be like this:

bool flag = false;
void f(int ind, vector<int> &ds, int s, int sum, int arr[],int n){
  if(ind == n){
    if(s == sum && flag == false){
      flag = true;
      for(auto it:ds) cout<<it<<" ";
      cout<<endl;
    }
    return;
  }
  ds.push_back(arr[ind]);
  s+= arr[ind];
  f(ind+1,ds,s,sum,arr,n);
  s-= arr[ind];
  ds.pop_back();
  f(ind+1,ds,s,sum,arr,n);
}

int main(){
  int arr[]={1,2,1};
  int n  = 3;
  int sum =2;
  vector<int> ds;
  f(0, ds, 0, sum, arr, n);
  return 0;
}
```
## This above code is something which is not preffered.
## The technique to print only one answer: You will write the function and in the base case, if the condition is satisfied you will return true else false. This is the base case trick. Whenever you are doing a function call put that into a if condition and Whenever it satisfied simply return.
```cpp

bool f(int ind, vector<int> &ds, int s, int sum, int arr[],int n){
  if(ind == n){
    if(s == sum){
      for(auto it:ds) cout<<it<<" ";
      cout<<endl;
      return true;
    }
    return false;
  }
  ds.push_back(arr[ind]);
  s+= arr[ind];
  if(f(ind+1,ds,s,sum,arr,n) == true) return true;
  s-= arr[ind];
  ds.pop_back();
  if(f(ind+1,ds,s,sum,arr,n)== true) return true;
  return false;
}

int main(){
  int arr[]={1,2,1};
  int n  = 3;
  int sum =2;
  vector<int> ds;
  f(0, ds, 0, sum, arr, n);
  return 0;
}
```

## Printing number of subsequences present in given array whose sum is k
- ### base case:
    - ### return 1: condition satisfied
    - ### return 0: condition not satisfied
- ### l = f()
- ### r = f()
- ### return l + r;

```cpp

int f(int ind, int s, int sum, int arr[],int n){
  if(ind == n){
    if(s == sum){
      return 1;
    }
    return 0;
  }
  
  s+= arr[ind];
  int r = (ind+1,s,sum,arr,n);
  s-= arr[ind];
  int l = f(ind+1,s,sum,arr,n);
  return l + r;
}

int main(){
  int arr[]={1,2,1};
  int n  = 3;
  int sum =2;
  vector<int> ds;
  cout<<f(0, 0, sum, arr, n)<<endl;
  return 0;
}
```