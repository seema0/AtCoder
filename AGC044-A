#pragma GCC optimize("Ofast")
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
#define rep(i,n) for(ll i=0;i<n;i++)
#define rep2(i,a,b) for(ll i=(a);i<(b);++i)

template<class T> inline void chmin(T& a, T b) {if (a > b) a = b;}
template<class T> inline void chmax(T& a, T b) {if (a < b) a = b;}

ll N,A,B,C,D;
map<ll,ll> memo;
ll ret(ll n) {
  if (memo.find(n)!=memo.end()) return memo[n];
  if (n==0) return 0;
  if (n==1) return D;

  ll ans = min({
  ret(n/2)+A+n%2*D,
  ret(n/3)+B+n%3*D,
  ret(n/5)+C+n%5*D,
  });
  if (n%2>0) chmin(ans,ret((n+1)/2)+A+D);
  if (n%3>0) chmin(ans,ret((n+2)/3)+B+(3-n%3)*D);
  if (n%5>0) chmin(ans,ret((n+4)/5)+C+(5-n%5)*D);
  if (ans/n>=D) chmin(ans,n*D);
  
  memo[n]=ans;
  return ans;
}


int main() {
  int T;
  cin >> T;
  rep(i,T) {
    cin >> N >> A >> B >> C >> D;
    cout << ret(N) << endl;
    memo.clear();
  }
}
