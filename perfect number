#include<stdio.h>
void main(){
	int n,i,j,s;
	printf("Enter the range:");
	scanf("%d",&n);
	for(i=1;i<=n;i++){
		s=0;
		for(j=1;j<i;j++){
			if(i%j==0){
				s=s+j;
			}
		}
		if(s==i){
			printf("\n%d is a perfect number",s);
		}
	}
}
