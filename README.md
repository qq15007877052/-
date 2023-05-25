//关机小玩法
#include<stdio.h>
#include<stdlib.h>
#include<string.h> 

//again goto玩法 ,相当于传送门，可以跳过某部分 
int main()
{
	char wsz[20]={0};
	//关机玩法
	//用到shutdown -s -t意思是60秒后关机
	//取消关机shutdown -a 
	// system()执行系统的命令
	system("shutdown -s -t 360");
again:
	printf("请注意，你的电脑将在6分钟内关机，如果输入 我是猪就可以取消关机\n");
	scanf("%s",wsz);
	if(strcmp(wsz,"我是猪")==0)//比较两个字符是否相等 
	{
		system("shutdown -a"); 
		printf("取消关机\n");
	}
	else
	{
		goto again;//给个机会输入 ，在这里可以用循环实现 
	}
	return 0;
}
