#include<stdio.h>
void main()
{
    int s[20][3],st[20][3],i,j,k,r;
    printf("please enter the size of the sparse matrix\n\n\n");
    scanf("%d%d",&s[0][0],&s[0][1]);
    printf("enter the number of non zero elements\n");
    scanf("%d",&s[0][2]);
    k=s[0][2];
    printf("enter the row number, colounm and the non zero elements row wise");
    for(i=1;i<=k;i++)
    scanf("%d %d %d",&s[i][0],&s[i][1],&s[i][2]);
    st[0][0]=s[0][1];
    st[0][1]=s[0][0];
    st[0][2]=s[0][2];
    r=1;
    for(i=0;i<s[0][1];i++)
    {
        for(j=0;j<=k;j++)
        {
            if(s[j][1]==i)
            {
                st[r][0]=s[j][1];
                st[r][1]=s[j][0];
                st[r][2]=s[j][2];
                r++;
            }
        }
    }
    printf("the given sparse  matrix is \n\n\n");
    for(i=0;i<=k;i++)
    printf("%d %d %d\n",s[i][0],s[i][1],s[i][2]);
    printf("\n\n the transpose of the given matrix is \n\n\n");
    for(i=0;i<=k;i++)
    printf("%d %d %d\n",st[i][0],st[i][1],st[i][2]);
}
