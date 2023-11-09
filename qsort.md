# qsort快速排序和sizeof运算符
## 一.qsort快速排序
对于C语言中排序，冒泡排序是一种普遍常用的方法，但冒泡排序在绝大多数情况下只被用来整形排序，但在结构体等内容中我们常用到char,float,double等非整形数据，此时，qsort快速排序不失为一个很好的选择。
### 1.头文件
```go
   #include<stdlib.h>
```
![Git Bush](https://antansit.oss-cn-shanghai.aliyuncs.com/img/qsort1.png)
### 2.qsort函数的格式
![Git Bush](https://antansit.oss-cn-shanghai.aliyuncs.com/img/qsort2.png)
根据官方网站，qsort传值由四部分构成
a.void* base
第一个参数是一个指针，通常指向需要排序的数组（可用数组名代替）或对象
b.size_z num
第二个参数是一个整形数字，表示需要排序的对象元素个数。
c.size_size
第三个参数为元素的大小（具体格式详见 二.sizeof）
d.int (*compar)(const void*,const void*)
第四个参数是一个函数指针，指向实现排序的函数。（可用函数名代替）
### 3.cmp函数
qsort快速排序需要一个函数实现为qsort返回值。
常为
```go
   int cmp(const void* e1,const void*e2)//设成空指针，方便接受不同类型变量的地址。
   {
      return (int*)e1-(int*)e2;//强制类型转换，取决于需要排序的变量类型
   }
```
若返回值不是整形，则要多加一个强制类型转化，将返回值转化为整形，
```go
   int cmp(const void* e1,const void*e2)
   {
      return （int）(double*)e1-(double*)e2）;
   }
```
根据C语言对真假的处理，qsort快速排序默认升序，若要降序排列，可以改变返回值。
```go
   int cmp(const void* e1,const void*e2)
   {
      return (int*)e2-(int*)e1;
   }
```
或自定义返回值
```go
   int cmp(const void* e1, const void* e2)//升序
  {
	  int* p1 = (int*)e1;//也可定义新的整形变量存放强制类型转化后的空指针。
	  int* p2 = (int*)e2;
	  if (*p1 > *p2)
	  {
		  return 1;
	  }
	  else if (*p1 == *p2)
	  {
		  return 0;
	  }
	  else if (*p1 < *p2)
	  {
		return -1;
	  }
  }
```
## 二.sizeof（针对qsort）
在qsort传值时，第三个参数为排序对象的大小。下列几种格式。
### 1.sizeof（变量类型）
例如sizeof（int）
### 2.sizeof（变量名）
在某些排序中，变量类型为结构体变量等，无法使用第一种方法。此时我们可以使用sizeof（变量名）。
```go
typedef struct Stu
{
   int num;
   int score;
   int math;
   int eng;
   int C;
}Stu;
int main()
{
   qsort(list, n, sizeof(Stu), cmp);
   return 0;
}
```
### 3.字节数
此处变量大小也可以写成字节数。
```go
qsort(list, n, 4, cmp);//int
```
```go
qsort(list, n, 1, cmp);//char
```
总而言之，qsort快速排序相比于冒泡排序更加全面广泛，但理解和操作起来较困难，可在编写程序时合理选择。
