# stone-paper-scissors-game
//stone paper scissors game
#include <stdio.h>
#include <stdlib.h>
int main()
{
	int i, n,t, c , u;
	c=0;
	u=0;
	char name[50];
	FILE *fh;
	fh=fopen("sps game.txt","a");
	printf("\tSTONE PAPER SCISSORS GAME\n");
	printf("\t*\n\n");
	printf("\t1 for stone,2 for paper,3 for scissors\n\n");
	printf("enter your name\n");
	scanf("%s",name);
	for(t=1;t<=5;t++)
	{
		printf("enter your choice\n");
	    scanf("%d",&n);
   	    i=(rand() % 3) + 1;
   	    printf("computers choice\n");
   	    printf("%d",i);
   	    printf("\n");
     	if (i==3 && n==2)
     	{
     	     c++;
              printf("point is for computer\n");
     	}
    	if (i == 1 && n == 2)
    	{
    	    u++;
		    printf("point is for u\n");
    	}
  	    if (i == 2 && n == 1)
  	    {
  	      c++;
    	    printf("point is for computer\n");
  	    }
        if (i == 1 && n == 3 )
        {
            c++;
            printf("point is for computer\n");
         	c+=1 ;
        }
  	    if (i == 3 && n == 1)
  	    {
  	         u++;
               printf("point is for u\n");
  	    }
      	if (i ==2 && n==3)
      	{
      	   u++;
     	    printf("point is for u\n");
      	}
      	if (i==n)
      	{
			printf("draw ,try once again\n");
      	}
	}
	printf("final point for computer\n");
	printf("%d",c);
	printf("\n");
	printf("final point for u\n");
	printf("%d",u);
	printf("\n");
	fprintf(fh,"%ss recent point\n",name);
	fprintf(fh,"%d\n",u);
	if (c>u)
	{
	printf("computer won the match\n");
	}
	if (c<u)
	{
	printf("%d won the match\n",name);
	}
	if (c==n)
	{
	printf("draw match\n");
	}
    fclose(fh);
}
