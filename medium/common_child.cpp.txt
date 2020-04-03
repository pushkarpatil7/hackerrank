#include<bits/stdc++.h>
using namespace std;
#define ll long long
#define N 5001
int dp[N][N];

ll solve(string s1,string s2,int n,int m){

    for(int i=0;i<=n;i++){
      for(int j=0;j<=m;j++){

          if(i==0||j==0)
          dp[i][j]=0;

          else if(s1[i-1]==s2[j-1]){
              dp[i][j]=dp[i-1][j-1]+1;
          }
          else
          dp[i][j]=max(dp[i-1][j],dp[i][j-1]);
      }
    }
    return dp[n][m];
}
int main(){

    ios_base::sync_with_stdio(false);cin.tie(0);cout.tie(0);

    string s1,s2;
    cin>>s1>>s2;


    ll ans = solve(s1,s2,s1.length(),s2.length());
    cout<<ans<<"\n";
}
