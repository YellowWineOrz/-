# -#include<bits/stdc++.h>
using namespace std;
int a[100001];
int t=1;
int o=1;
int r,m;
int n,k; 
int sum1=0;
string st;
char first;
int def(int j)
{
	int x=0;
	for(int i=1;i<=o;i++){
		x+=(a[i]/(j+1));
	}
	if(x<=k)
		return true;
	else
		return false;
}
void abc()
{
	if(first=='N')
		first=='F';
	else
		first=='N';
}

int main()
{
	//freopen("P3718.in","r",stdin);
	int l=2,mid;//——————————————— 
	int cnt=0;//
	cin>>n>>k;
	cin>>st;
	first=st[0];
	a[1]=1;
	/*for(int i=0;i<n;i++)
	{
		if(st[i]!=first)cnt++;
		abc();
		cout<<"ST:"<<st[i]<<endl;
	}
	if(cnt<=k)
	{
		cout<<1;
		return 0;
	}*/
	first=st[0];
	for(int i=1;i<n;i++)
	{
		if(st[i]==first)
			a[o]++;
		else{
			a[o++]=1;
			abc();
		}	
	}
	for(int i=1;i<=o;i++){
	//	cout<<"Ye";
		r=max(r,a[i]);
	}
	while(l<=r){
		mid=(r+l)/2;
	//	cout<<"mid:"<<mid<<endl;//	
		if(def(mid))
			r=mid-1;
		else
			l=mid+1;
			//cout<<"l:"<<l<<endl;//

	}
	cout<<l;
	//cout<<cnt;//
}
