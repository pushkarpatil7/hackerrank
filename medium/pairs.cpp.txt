#include<bits/stdc++.h>
using namespace std;
#define ll long long
int main(){

    ios_base::sync_with_stdio(false);cin.tie(0);cout.tie(0);

    ll n,k;
    cin>>n>>k;

    map<ll,ll>mp;

    ll a[n];
    for(int i=0;i<n;i++){
    cin>>a[i];
    mp[a[i]]++;
    }

    sort(a,a+n);
    ll ans=0;
    for(int i=0;i<n;i++){
        if(mp[k+a[i]])
        ans+=mp[k+a[i]];
    }
    cout<<ans<<"\n";
}
