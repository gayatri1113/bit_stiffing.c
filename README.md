//# bit_stiffing.c//
#include<stdio.h>
#include<string.h>
void main()
{
    char a[100];
    int count=0,i,j,l,k;
    printf("Enter a input string:");
    scanf("%s",&a);
    l=strlen(a);
    for(i=0;i<l;i++)
    {
        if(a[i]=='l')
        {
            k=i;
            count=0;
            while(a[k]=='l')
            {
                count+=1;
                k++;
                {
                     for(j=l+1;j>k;j--)
                    {
                        a[j]=a[j-1];
                    }
                    a[k]='0';
                    l++;
                    break;
                }   
                i=k; 
            }
            
        }
    }
    printf("\nthe bitstuffed string is %s",a);
    k=0;
    for(i=0;i<=l;i++)
    {
        if(a[i]=='l')
        {
            k=i;
            count=0;
            while(a[k]=='l')
            {
                count+=1;
                k++;
                if(count==5)
                {
                    for(j=k;j<l+1;j++)
                    {
                        a[j]=a[j+l];
                    }
                    l--;
                    a[l+1]='0';
                    break;
                }
            }
            i=k-1;
        }
    }
    printf("string after unstuffing %s\n",a);
}
