# get-kth-number-in-mountain-array


#include<bits/stdc++.h>

using namespace std;

int getpivet(vector<int>&v, int start, int end) {
    
    int mid=start+((end-start)/2);
      
    while(start<end)  {
        
      
        if(v[0]<=v[mid])  start=mid+1;
        
        else      end=mid;
        
        mid=start+((end-start)/2);
        
    }
    return start;
    
}

  int getbinary(vector<int>v,int start,int end,int number){
      
      
      int mid=start+((end-start)/2);
      
      while(start<=end)  {
          
        if(v[mid]==number)  return mid;
          
         else if(v[mid]>number)  end=mid-1; 
         
         else         start=mid+1;
          
          mid=start+((end-start)/2);
          
      }
      
  }

int main() {
    
    int n, x, mid, number, bs;
    cin>>n>>number;
    vector<int>v;

    for(int i=0;i<n;i++) {
        
        cin>>x;
        v.push_back(x);
        
    } 
    int start=0, end=n-1;
     
    int pivet=getpivet(v,start,end);
    
    if(v[pivet]<=number && number<=v[n-1])  
    
                    bs=getbinary(v,pivet,end,number);
    
    else       bs=getbinary(v,start,pivet-1,number);
   
    
    cout<<bs;
}
