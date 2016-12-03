#include <bits/stdc++.h>
using namespace std;
const int N = 200005;
int cc,n,a,b,c,m;
int pos;
int pa[N],ran[N];
int fib[N],isf[N];
struct nd 
{
    int a,b,c;
}s[N];
int cmp(nd a,nd b)  {return a.c<b.c;}
int cmp2(nd a,nd b) {return a.c>b.c;}
void ini()
{
    pos=0;
    memset(s,0,sizeof(s));
    for (int i=0;i<=n;i++)
        pa[i]=i,ran[i]=1;
}
int find(int x)
{
    if (pa[x]==x)
        return x;
    return pa[x]=find(pa[x]);
}
void uni(int a,int b)
{
    int x=find(a),y=find(b);
    if (x!=y)
    {
        if (ran[x]<ran[y])
            pa[x]=y;
        else
        {
            pa[y]=x;
/*
            if (ran[x]==ran[y])
                ran[x]++;
*/
        }
    }
}
int same(int x,int y)
{
    if (find(x)==find(y))
        return 1;
    return 0;
}
int kru1()
{
    int ans=0;
    sort(s,s+m,cmp);
    for (int i=0;i<m;i++)
    {
        int x=s[i].a,y=s[i].b;
        if (!same(x,y))
        {
            uni(x,y);
            ans+=s[i].c;
        }
    }
    return ans;
}
int kru2()
{
    int ans=0;
    sort(s,s+m,cmp2);
    for (int i=0;i<m;i++)
    {
        int x=s[i].a,y=s[i].b;
        if (!same(x,y))
        {
            uni(x,y);
            ans+=s[i].c;
        }
    }
    return ans;
}
int main()
{
    scanf("%d",&cc);
    int cas=1;
    memset(isf,0,sizeof(isf));
    isf[1]=1;
    fib[0]=1;
    fib[1]=1;
    for (int i=2;i<N;i++)
    {
        fib[i]=fib[i-1]+fib[i-2];
        if (fib[i]<N)
            isf[fib[i]]=1;
        else 
            break;
    }
    
    while(cc--)
    {
        scanf("%d%d",&n,&m);        
        ini();
        for (int i=0;i<m;i++)
        {
            scanf("%d%d%d",&a,&b,&c);
            s[i].c=c;
            s[i].a=a;
            s[i].b=b;
        }
        int l=kru1();
        for (int i=0;i<=n;i++)
            pa[i]=i,ran[i]=1;
        int r=kru2();
        int f=0;
        for (int i=l;i<=r;i++)
            if (isf[i])
            {
                f=1;
                break;
            }
/*        
        for (int i=0;i<=n;i++)
            cout<<i<<" "<<pa[i]<<endl;
*/
//        cout<<l<<" "<<r<<" "<<endl;
        int tp=pa[1];
        for (int i=1;i<=n;i++)
            if (tp!=pa[i])
            {
                f=0;
                break;
            }
        
        printf("Case #%d: ",cas++);
        if (f)
            printf("Yes\n");
        else
            printf("No\n");
    }
    return 0;    
} 
/*
4
4 2
1 2 1
3 4 1

4 4
1 2 1
2 3 1
3 4 1
1 4 0
5 6

1 2 1
1 3 1
1 4 1
1 5 1
3 5 1
4 2 1

*/
