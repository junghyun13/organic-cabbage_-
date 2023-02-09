# organic-cabbage_-
# c
0은 배추가 심어져 있지 않은 땅이고, 1은 배추가 심어져 있는 땅을 나타낸다. 입력의 첫 줄에는 테스트 케이스의 개수 T가 주어진다. 그 다음 줄부터 각각의 테스트 케이스에 대해 첫째 줄에는 배추를 심은 배추밭의 가로길이 M과 세로길이 N, 그리고 배추가 심어져 있는 위치의 개수 K이 주어진다. 그 다음줄은 x와y로 배추가 있는 위치를 가르킨다. 각 테스트 케이스에 대해 필요한 최소의 해충방지의 배추흰지렁이 마리 수를 출력하는 프로그램을 작성해보자!

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int map[100][100],visited[100][100];
int dx[4]={-1,1,0,0};
int dy[4]={0,0,-1,1};
int m,n,k;


void dfs(int a,int b){
	int i;
	visited[a][b]=1;
	for(i=0;i<4;i++){
		int x=a+dx[i];
		int y=b+dy[i];
		if(x<0 || x>=m || y<0 || y>=n){ //map의 범위에서 벗어난 부분은 다시  
			continue;}
		if(map[x][y]==1 && visited[x][y]==0){
			dfs(x,y);}}}
			
			
void init(){
	int i,j;
	for(i=0;i<100;i++){
		for(j=0;j<100;i++){
			map[i][j]=0;
			visited[i][j]=0;}}}



int main(){
	int t,cnt;
	scanf("%d",&t);
	int i,j,count=0;
	while(count!=t){
	    cnt=0;
	    scanf("%d %d %d",&m,&n,&k);
	    for(i=0;i<k;i++){
		int a,b;
		scanf("%d %d",&a,&b);
		map[b][a]=1;}
	    for(i=0;i<n;i++){
		    for(j=0;j<m;j++){
			    if(map[i][j]==1 && visited[i][j]==0){
				dfs(i,j);
				cnt++;}}}
	count++;
	printf("최소의 배추지렁이의 수: %d\n",cnt);}
	return 0;}
