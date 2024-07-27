Subarray with sum equal to Zero in C++
Here, in this page we will discuss the program to find if there is any subarray with sum equal to zero in C++ programming language. If such subarray is present then print true otherwise print false.

subarray with sum equal to 0 in C++
Method Discussed :
Method 1 : Naive Approach
Method 2 : Using Hashing
Method 1 :
Run a outer loop for index 0 to n.
Run a nested loop from index i+1 to n,
Find sum, if it is equal to 0, then print true.
Otherwise, print false.
Time and Space Complexity
Time Complexity : O(n2)
Space Complexity : O(1)
Run
#include<bits/stdc++.h>
using namespace std;

int main(){
    int arr[] = {-3, 2, 3, 1, 6};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    int flag = 0, sum;
    
    for(int i=0; i<n; i++){
      
        for(int j=i; j<n; j++){
            sum += arr[j];
            
            if(sum==0){
                flag =1;
                break;
            }
        }
    }
    
    if(flag==1)
    cout<<"true";
    
    else cout<<"false";
    
}
Output
false
Method 2 :
Iterate through the array and for every element arr[i],
Calculate the sum of elements from 0 to i.
If the current sum has been seen before, then there is a zero-sum array.
Hashing is used to store the sum values so that we can quickly store sum.
Check out whether the current sum is seen before or not.
Time and Space Complexity
Time Complexity : O(n2)
Space Complexity : O(1)
Run
#include<bits/stdc++.h>
using namespace std;

int main(){
    int arr[] = {-3, 2, 3, 1, 6};
    int n = sizeof(arr)/sizeof(arr[0]);
    int flag = 0, sum = 0;
    
    set<int>st;
    
    for(int i=0; i<n; i++){
        
         sum += arr[i];
         if (sum == 0 || st.find(sum) != st.end()){
            flag=1;
            break;
         }
 
        st.insert(sum);
    }
    
    
    if(flag==1)
    cout<<"true";
    
    else cout<<"false";
    
}
Output
false
