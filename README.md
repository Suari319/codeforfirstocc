#include <iostream>
#include<vector>
using namespace std;
int findfirstocc(vector<int>arr,int target){
 int start=0;
 int end=arr.size()-1;
  int mid=start+(end-start)/2;
  int ans=-1;
  while(start<=end){
    if(arr[mid]==target){
      ans=mid;
      end=mid-1;
    }
    else if(arr[mid]<target){
      start=mid+1;
    }
    else
      end=mid-1;
    mid=start+(end-start)/2;
  }
  return ans;
}

int main() {
  vector<int>arr{1,2,3,3,3,3,4,};
  int target;
  target=3;
  int ans=findfirstocc(arr,target);
  cout<<ans;
}
