#include <bits/stdc++.h>
using namespace std;

bool safe(int i, int j,int m,int n)
{
    if(i<0 || j<0 || i>=m || j>=n )
        return false;
    return true;   
}

void adjacent(vector<vector<int>> & field)
{
      int m=field.size();
    int n=field[0].size();
    int row[4]={-1,1,0,0};
    int col[4]={0,0,-1,1};
    
   for(int i=0;i<m;i++)
     {
      for(int j=0;j<n;j++)
      {
          for(int k=0;k<4;k++)
          {
             if(safe(i+row[k],j+col[k],m,n) 
                && field[i][j]==0)
                 field[i+row[k]][j+col[k]]=-1;
           }
      }      
    }
     for(int i=0;i<m;i++)
      for(int j =0;j<n;j++)
       if(field[i][j]==-1)
           field[i][j]=0;
    
}

int SP(vector<vector<int>> &field , int i, int j,int &result,int temp_res)
{
    
     int m=field.size();
    int n=field[0].size();
    
    if(j==n-1 )
    {
        if(temp_res<result)
            result=temp_res;
        return 0;
    }
     
     field[i][j]=0;
    
    if(safe(i,j+1,m,n) 
      && field[i][j+1]==1)
        SP(field,i,j+1,result,temp_res+1);
    
     if(safe(i+1,j,m,n) 
      && field[i+1][j]==1)
        SP(field,i+1,j,result,temp_res+1);
    
    if(safe(i-1,j,m,n) 
      && field[i-1][j]==1)
        SP(field,i-1,j,result,temp_res+1);
    
    field[i][j]=1;
    
    return 0;

}

int shortestPath(vector<vector<int>> &field)
{ 

    int m=field.size();
    int n=field[0].size();
    
     adjacent(field);
 
    for(int i=0;i<m;i++)
    {
      for(int j=0;j<n;j++)
      cout<<field[i][j]<<" ";
        cout<<"\n";
    }
    
     int result=20;
                
         for(int i=0;i<m;i++)
             if(field[i][0]==1)
       SP(field,i,0,result,0);
                
 
    return result;
}


int main() 
{
	vector<vector<int>>v={
        { 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 },
        { 1, 0, 1, 1, 1, 1, 1, 1, 1, 1 },
        { 1, 1, 1, 0, 1, 1, 1, 1, 1, 1 },
        { 1, 1, 1, 1, 0, 1, 1, 1, 1, 1 },
        { 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 },
        { 1, 1, 1, 1, 1, 0, 1, 1, 1, 1 },
        { 1, 0, 1, 1, 1, 1, 1, 1, 0, 1 },
        { 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 },
        { 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 },
        { 0, 1, 1, 1, 1, 0, 1, 1, 1, 1 },
        { 1, 1, 1, 1, 1, 1, 1, 1, 1, 1 },
        { 1, 1, 1, 0, 1, 1, 1, 1, 1, 1 }};
        
        
    cout<<"The shortest path length is "<<shortestPath(v)<<endl;
	return 0;
}


// Time complexity:- O(n*m+n*4^(n*m))
// Space complexity:- O(4^(n*m))
