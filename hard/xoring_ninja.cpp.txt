#include<bits/stdc++.h>
using namespace std;
#define ll long long
#define mod 1000000007

ll power(ll n , ll m) {

    ll ans = 1;
    m%=mod;

    while(m) {
        if(m&1) ans = (ans%mod * n%mod) %mod;

        m = m>>1;
        n = (n * n)%mod;
    }

    return ans;

}

int main() {

    ios_base::sync_with_stdio(false);cin.tie(0);cout.tie(0);

    ll t;
    cin>>t;

    while(t--) {
        ll n;
        cin>>n;

        ll a;

        ll ans = 0;

        for(int i=0;i<n;i++) {
            cin>>a;
            ans |= a;
        }

        ans *= power(2,n-1);
        ans%=mod;
        cout<<ans<<"\n";

    }
    return 0;
}
