# ProjectObjectC03

int* fun(){

    int* p=malloc(100*sizeof(int));
    
    return p;
    
}

int* creatIntArray(int num){

    int* p=malloc(num*sizeof(int));
    
    return p;
}
int main(int argc, const char * argv[]) {

    int* p=malloc(10*sizeof(int));//分配10个int空间大小  可以把这个当作数组一样去操作
    
    //开辟了一个10个int大小的数组空间大小 数组的首地址 是p
    
    p[0]=100;
    
    p[1]=200;
    
    for (int n=0;  n<3; n++) {
    
        printf("values:%d \n",p[n]);
        
    }
    
    free(p);
    
    //如果一个函数 返回一个堆内存 那么基本就是开辟了堆内存 因为栈内存 随着函数使用完毕 就销毁了
    int* point=fun();
    
    point[0]=100;
    
    point[1]=200;
    
    for (int n=0;  n<3; n++) {
    
        printf("values:%d \n",point[n]);
    }
    
    free(point);
    
    
    //使用堆内存可以 动态的设置数组的长度大小
    
    int* array=creatIntArray(50);
    
    free(array);
    
    return 0;
}
