## SARAN M
## 212220230044
# <p align='center'>SIRI OR GOOGLE ASSISTANT</p>
## PROGRAM
```c
#include <stdio.h>
#include<string.h>
char name[9][1000]={"saran","Pradeep","Dinesh ","Kumaran ","Kumaravel ","Arun ","Tamizh ","Loghul "};
void call(int m,int n,char str3[],char str[]);
void message(int m,int n,char str3[],char str[],char str4[]);
void musik1(char xx[],int var);
void musik2(char y[],int var);
void musik(char y[]);
void musi();
void main1();
int main()
{
    main1();
    return 0;
}
void main1()
{
    int i,j,n,m;
    char str[1000],str2[1000],str3[1000], str4[1000];
    printf("Enter the opeartion:\n");
    scanf("%[^\n]s",str);
    getchar();
    n=strlen(str);
    
    for(i=0;str[i];i++)
    {
        if(str[i]==' ')
        {
            break;
        }
        str2[i]=str[i];
    }
    m=strlen(str2);
    if(strcmp(str2,"call")==0)
    {
        call(m,n,str3,str);
    }
    else if(strcmp(str2,"message")==0)
    {
        message(m,n,str3,str,str4);
    }
    else if(strcmp(str2,"play")==0)
    {
        musi();
    }
    
}
void musi()
{
    char mus_ic[50];
    printf("Which music you want to play:\n");
    scanf("%[^\n]s",mus_ic);
    musik(mus_ic);
}
void musik1(char xx[],int var)
{
    char re[50];
    if(strcmp(xx,"yes")==0)
    {
        
        printf("Which Song you want to play\n");
        scanf("%s",re);
        if(strcmp(re,"previous")==0){
            var=var-1;
            musik2(re,var);
        }
        else if(strcmp(re,"next")==0){
            var=var+1;
            musik2(re,var);
        }
        else{
            musik(re);
        }
        
    }
    else
    {
        printf("\n\t\t\t\t\t\tThank You..!!!!");
        
    }
    
}
void musik2(char y[],int var)
{
    char music[100][100]={"mu","Thee","Annul","Jimikki","Va"};
    int n=sizeof(music)/sizeof(music[0]);
    if(n<var)
    printf("This is the Last song");
    else if(var<0){
        printf("This is the first song\n");
    }
    else
    printf("Playing %s",music[var]);
    printf("\n\nDo you want you want to continue\n");
    char yy[20];
    scanf("%s",yy);
    musik1(yy,var);
}
void musik(char y[])
{
    char music[100][100]={"mu","Thee","Annul","Jimikki","Va"};
    int flag=0,n=sizeof(music)/sizeof(music[0]),var;
    static int i=0;
    for(i=0;i<n;i++)
    {
        if(strcmp(music[i],y)==0)
        {
             printf("Playing %s",music[i]);
             var=i;
             flag=1;
        }
        
    }
    if(flag==0)
    {
        printf("\nThe song is not in the list");
    }
    printf("\n\nDo you want you want to continue\n");
    char yy[20];
    scanf("%s",yy);
    musik1(yy,var);
}


void call(int m,int n,char str3[],char str[])
{
    int i,j;
    for(i=m+1;i<n;i++)
        {
            str3[i-(m+1)]=str[i];
        }
        for(j=0;j<7;j++)
            {
                if(strcmp(str3,name[j])==0)
                {
                    printf("Calling %s",str3);
                }
            }
    
}
void message(int m,int n,char str3[],char str[],char str4[])
{
    int j=0,i;
        for(i=m+1;i<n;i++)
        {
            str3[j++]=str[i];
        }
        for(j=0;j<7;j++)
            {
                if(strcmp(str3,name[j])==0)
                {
                    printf("Enter message:");
                    scanf("%[^\n]",str4);
                    getchar();
                    printf("The Message '%s' sent to %s succesfully",str4,str3);
                }
            }
}
```
