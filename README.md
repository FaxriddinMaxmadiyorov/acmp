# acmp
Solutions of problems on acmp.ru
#include <bits/stdc++.h>
#define ll long long 

using namespace std;

int main ()
{
	ll n, cnt, x=0; cin>>n>>cnt;
	ll a[n+1][n+1];
	for (int i=1; i<=n; i++){
		for (int j=1; j<=n; j++)
			cin>>a[i][j];
	}
	stack<ll> t;
	t.push(cnt);
	bool v[n+1]={0};
	v[cnt]=true;
	while (true){
		ll s=t.top();
		bool f=false;
		for (int i=1; i<=n; i++){
			if (a[s][i]==1 && v[i]==false){
				v[i]=true;
				t.push(i);
				f=true;
				break;
			}
		}
		if (f==false)
			t.pop();
		if (t.empty())
			break;
	}
	for (int i=1; i<=n; i++){
		if (v[i]==true){
			x++;
		}
	}
	cout<<--x;
}
