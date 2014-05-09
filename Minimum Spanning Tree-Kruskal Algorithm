#include <stdio.h>
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;
struct edge
{
    int u , v;
    long long w;
};
vector <edge> graph;
int parent[10000+10];
int find_parent(int x)
{
    if(parent[x]==x) return x;
    else return parent[x]=find_parent(parent[x]);
}
bool cmp(edge a,edge b)
{
    return a.w<b.w;
}
long long MST(int N)
{
    for(int i=1;i<=N;i++) parent[i]=i;
    sort(graph.begin(),graph.end(),cmp);
    int cnt = 0;
    long long answer=0;
    for(int i=0;i<graph.size();i++)
    {
        int x = find_parent(graph[i].u);
        int y = find_parent(graph[i].v);
        if(x!=y)
        {
            parent[x]=y;
            cnt++;
            answer=answer+graph[i].w;
        }
        if(cnt==N-1) break;
    }
    if(cnt!=N-1) return -1;
    return answer;
}
int main()
{
    int N,M;
    scanf("%d%d",&N,&M); // N number of Vartexes // M number of edges
    while(M--)
    {
        int i , j ;
        long long k;
        scanf("%d%d%lld",&i,&j,&k); // between i and j nodes weight is k
        edge get;
        get.u=i;get.v=j;get.w=k;
        graph.push_back(get);
    }
    cout<<MST(N)<<"\n";
    return 0;
}
