
#include <iostream>

using namespace std;
typedef int(*mathfunc)(int,int);

int add(int a, int b, int c)
{
    return a+b;
}
int sub(int a,int b){
    return a-b;
}
//int (*getFunc(int v))(int,int) {
mathfunc getFunc(int v) {
    if(v==1)
        return sub;
    else
        return sub;
}

int (*passfunc(int(*v)(int,int)))(int,int)
{
    int(*ret)(int,int) = *v;
    return ret;
}
int main()
{
    //cout<<"Hello World";
    mathfunc m = NULL;
    int (*i)(int,int) = passfunc(sub);
    
    cout<<i(8,3)<<endl;
    //int (*arrFunc[2])(int,int) = {add,sub};
    m = getFunc(2);
    cout<<m(1,2)<<endl;
    int (*test)(int,int,int);
    test = add;
    cout<<test(1,2,5)<<endl;
    //cout<<(*arrFunc[0])(3,4)<<endl;
    //cout<<(*arrFunc[1])(8,3)<<endl;
    return 0;
}
