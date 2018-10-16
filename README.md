# Assignment-2-OS
## Create an array of 1000 and create 10 child processess and show their sum in parent process:
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
int main(int argc , char *argv){
int sum1,sum2,sum3,sum4,sum5,sum6,sum7,sum8,sum9,sum10;
int arr[1000];
int fd[2];
int fd1[2];
int fd2[2];
int fd3[2];
int fd4[2];
int fd5[2];
int fd6[2];
int fd7[2];
int fd8[2];
int fd9[2];

pipe(fd);
pipe(fd1);
pipe(fd2);
pipe(fd3);
pipe(fd4);
pipe(fd5);
pipe(fd6);
pipe(fd7);
pipe(fd8);
pipe(fd9);
for(int i=0;i<1000;i++)
arr[i]=i;
int cpid1=fork();
if(cpid1<0)
{
printf("Child Process 1 failed");
exit(-1);
}
else if(cpid1==0)
{
for(int i=0;i<100;i++)
sum1+=arr[i];
write(fd[1],&sum1,sizeof(int));
exit(0);
}
else
{
int cpid2=fork();
if(cpid2<0)
{
printf("Child Process 2 failed");
exit(-1);
}
else if(cpid2==0)
{
for(int i=100;i<200;i++)
sum2+=arr[i];
write(fd1[1],&sum2,sizeof(int));
exit(0);
}
else
{
int cpid3=fork();
if(cpid3<0)
{
printf("Child Process 3 failed");
exit(-1);
}
else if(cpid3==0)
{
for(int i=200;i<300;i++)
sum3+=arr[i];
write(fd2[1],&sum3,sizeof(int));
exit(0);
}
else
{
int cpid4=fork();
if(cpid4<0)
{
printf("Child Process 4 failed");
exit(-1);
}
else if(cpid4==0)
{
for(int i=300;i<400;i++)
sum4+=arr[i];
write(fd3[1],&sum4,sizeof(int));
exit(0);
}
else
{
int cpid5=fork();
if(cpid5<0){
printf("Child Process 5 failed");
exit(-1);
}
else if(cpid5==0)
{
for(int i=400;i<500;i++)
sum5+=arr[i];
write(fd4[1],&sum5,sizeof(int));
exit(0);
}
else
{
int cpid6=fork();
if(cpid6<0){
printf("Child Process 6 failed");
exit(-1);
}
else if(cpid6==0)
{
for(int i=500;i<600;i++)
sum6+=arr[i];
write(fd5[1],&sum6,sizeof(int));
exit(0);
}
else
{
int cpid7=fork();
if(cpid7<0){
printf("Child Process 7 failed");
exit(-1);
}
else if(cpid7==0)
{
for(int i=600;i<700;i++)
sum7+=arr[i];
write(fd6[1],&sum7,sizeof(int));
exit(0);
}
else
{
int cpid8=fork();
if(cpid8<0){
printf("Child Process 8 failed");
exit(-1);
}
else if(cpid8==0)
{
for(int i=700;i<800;i++)
sum8+=arr[i];
write(fd7[1],&sum8,sizeof(int));
exit(0);
}
else
{
int cpid9=fork();
if(cpid9<0){
printf("Child Process 9 failed");
exit(-1);
}
else if(cpid9==0)
{
for(int i=800;i<900;i++)
sum9+=arr[i];
write(fd8[1],&sum9,sizeof(int));
exit(0);
}
else
{
int cpid10=fork();
if(cpid10<0){
printf("Child Process 10 failed");
exit(-1);
}
else if(cpid10==0)
{
for(int i=900;i<1000;i++)
sum10+=arr[i];
write(fd9[1],&sum10,sizeof(int));
exit(0);
}
}
}
}
}
}
}
}
}
}
read(fd[0],&sum1,sizeof(int));
read(fd1[0],&sum2,sizeof(int));
read(fd2[0],&sum3,sizeof(int));
read(fd3[0],&sum4,sizeof(int));
read(fd4[0],&sum5,sizeof(int));
read(fd5[0],&sum6,sizeof(int));
read(fd6[0],&sum7,sizeof(int));
read(fd7[0],&sum8,sizeof(int));
read(fd8[0],&sum9,sizeof(int));
read(fd9[0],&sum10,sizeof(int));

printf("%d",sum1+sum2+sum3+sum4+sum5+sum6+sum7+sum8+sum9+sum10);
return 0;
}
