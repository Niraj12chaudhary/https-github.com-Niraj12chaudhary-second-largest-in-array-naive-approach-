# https-github.com-Niraj12chaudhary-second-largest-in-array-naive-approach
#include <iostream>
using namespace std;
int getlargest(int a[],int n)
{
    int largest=0;
    
    for(int i=1;i<n;i++)
    {
        if(a[i]>a[largest])
        {
            largest=i;
        }
    }
    return largest;
}

int secondlargest(int a[],int n)
{
    int largest=getlargest(a,n);
    int res=-1;
    
    for(int i=0;i<n;i++)
    {
        if(a[i]!=a[largest])
        {
            if(res==-1)
            res=i;
            else if(a[i]>a[res])
            res=i;
        }
    }
    return res;
}
int main() 
{
    int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++)
    {
        cin>>a[i];
    }
    int pos=secondlargest(a,n);
    cout<<pos<<endl;
    
	return 0;
    
}
