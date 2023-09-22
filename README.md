# test_9_22
#include <stdio.h>
#include <string.h>
//
//1、模拟用户登录情况
//int main(){
//	int i = 0;
//	char password[20]={0};
//	for(i=0;i<3;i++){
//		printf("请输入密码：>");
//		scanf("%s",password);
//		if(strcmp(password,"123456") == 0)
//		{
//			printf("密码正确/n");
//			break;
//		}
//		else
//		{
//			printf("密码错误/n");
//		}
//		if(i == 3)
//			printf("三次输入错误，退出程序/n");
//	}
//	return 0;
//}
//2、输出三个数，从大到小输出
//void tmp(int x,int y)
//{
//	int tmp = x;
//	x = y;
//	y = tmp;
//}
//int main(){
//	int a = 0;
//	int b = 0;
//	int c = 0;
//	scanf("%d%d%d",&a,&b,&c);
//	if(a<b)
//	{
//		int tmp = a;
//		a = b;
//		b = tmp;
//	}
//	if(a<c)
//	{
//		int tmp = a;
//		a = c;
//		c = tmp;
//	}
//	if(b<c)
//	{
//		int tmp = b;
//		b = c;
//		c = tmp;
//	}
//	printf("%d %d %d\n",a,b,c);
//	return 0;
//}
//3、打印1-100之间三的倍数
//int main()
//{
//	int i = 0;
//	for(i=1;i<=100;i++){
//		if(i%3 == 0)
//			printf("%d ",i);
//	}
//	return 0;
//}
//4、给定两个数，求最大公约数
//int main(){
//	int m = 0;
//	int n = 0;
//	int r = 0;
//	scanf("%d%d",&m,&n);
//	while(r = m%n)
//	{
//		m = n;
//		n = r;
//	}
//	printf("%d\n",n);
//	return 0;
//}
//5、打印1000-2000之间的闰年
//int main(){
//	int year = 0;
//	int count = 0;
//	for(year=1000;year<=2000;year++){
//		if((year%4 == 0 && year%100 != 0) || (year%400 == 0)){
//			count++;
//			printf("%d ",year);
//		}
//	}
//		printf("\ncount=%d\n",count);
//		return 0;
//}
//顺序查找（顺序查找静态分配）
//#define MaxSize 10
//typedef struct{
//	int data[MaxSize];
//	int Length;
//}SqList;
//void InitList(SqList &L){
//	int i = 0;
//	for(i=0;i<L.Length;i++){
//		L.data[i]=0;
//	}
//	L.Length = 0;
//}
//int main(){
//	int i=0;
//	SqList L={1,2,3,4,5,6,7,8,9};
//	InitList(L);
//	for(i=0;i<L.Length;i++)
//		printf("data[%d]=%d\n",L.data[i]);
//	return 0;
//}
////动态分配
//#include <stdlib.h>
//#define InitSize 10
//typedef struct{
//	int* data;
//	int MaxSize;
//	int Length;
//}SeqList;
//void InitList(SeqList &L){
//	L.data=(int*)malloc(sizeof(int)*InitSize);
//	L.Length = 0;
//	L.MaxSize = InitSize;
//}
//void IncreaseSize(SeqList &L,int len){
//	int* p = L.data;
//	L.data = (int*)malloc((L.MaxSize+len)*sizeof(int));
//	for(int i=0;i<L.Length;i++){
//		L.data[i]=p[i];
//	}
//	L.MaxSize = L.MaxSize + len;
//	free(p);
//}
//ElemType GetElem(SeqList L,int i){
//	return L.data[i-1];
//}
//ElemType LocateElem(SeqList L,int e){
//	int i = 0;
//	for(i=0;i<L.Length;i++){
//		if(L.data[i] == e)
//			return i+1;
//	}
//	return 0;
//}
//
//int main(){
//	SeqList L;
//	InitList(L);
//	IncreaseSize(L,5);
//	return 0;
//}
////插入操作
//bool ListInsert(Sqlist &L,int i,int e){
//	if(i<1 || i>L.Length+1)
//		return false;
//	if(MaxSize<=L.Length)
//		return false;
//	for(int j=L.Length;j>=i;j--)
//		L.data[j] = L.data[j-1];
//	L.data[i-1] = e;
//	L.Length++;
//	return true;
//}
////删除操作
//bool ListDelete(SqList &L,int i,int e){
//	if(i<1 || i>L.Length)
//		return false;
//	e = L.data[i-1];
//	for(int j=i;j<L.Length;j++)
//		L.data[j-1] = L.data[j];
//	L.Length--;
//	return true;
//}
//bool Del-Min(SqList &L,ElemType &value){
//	if(L.Length == 0)
//		return false;
//	value = L.data[0];
//	int pos = 0;
//	for(int i=0;i<L.Length;i++){
//		if(L.data[i] < value){
//			value = L.data[i];
//		    pos = i;
//		}
//	}
//	L.data[pos] = L.data[L.Length-1];
//	L.Length--;
//	return true;
//}
//逆置顺序表中所有元素
//void Reverse(Sqlist &L){
//	ElemType temp;
//	for(int i=0,i<L.Length/2;i++){
//		temp = L.data[i];
//		L.data[i] = L.data[L.Length-i-1];
//		L.data[L.Length-i-1] = temp;
//	}
//}
//void Del_x_1(Sqlist &L,ElemType x){
//	int k = 0;
//	for(int i=0;i<L.Length;i++){
//		if(L.data[i] != x){
//			L.data[k] = L.data[i];
//			k++;
//		}
//	}
//	L.Length = k;
//}
//线性表的链式存储
#include <stdio.h>
#include <stdlib.h>
typedef struct LNode{
	ElemType data;
	struct LNode* next;
}LNode,*LinkList;
bool InitList(LinkList &L){
	L == NULL;
	return true;
}
bool InitList(LinkList &L){
	L = (LNode*)malloc(sizeof(LNode));
	if(L == NULL)
		return false;
	L->next = NULL;
	return true;
}
bool Empty(LinkList L){
	if(L == NULL)
		return true;
	else
		return false;
}
bool Empty(LinkList L){
	if(L->next == NULL)
		return true;
	else
		return false;
}
//按位序插入
bool ListInsert(LinkList &L,int i,ElemType e){
	if(i<1)
		return false;
	LNode* p;
	int j=0;
	p = L;
	while(p != NULL && j<i-1)
	{
		p = p->next;
		j++;
	}
	if(p != NULL)
		return false;
	LNode* s = (LNode*)malloc(sizeof(LNode));
	s->data = e;
	s->next = p->next;
	p->next = s;
	return true;
}
int main(){
	LinkList L;
	InitList(L);
	return 0;
}
