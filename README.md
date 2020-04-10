# operating-sysstems-final-code
Question 3
#include <windows.h>
#include <iostream>
#define MAX_THREADS 1
using namespace std;

DWORD prime (LPVOID);
HANDLE hThreads [MAX_THREADS];
DWORD id [MAX_THREADS];
DWORD waiter;

DWORD WINAPI Prime(LPVOID Param)
{
    DWORD nu = (DWORD)Param;
    for (DWORD i=0;i<=nu;i++)
    {
        if((nu%2==0) ||(nu%3==0) || (nu%4==0)||(nu%5==0)||(nu%6==0)||  (nu%7==0)||(nu%8==0)||(nu%9==0))
        cout <<"";
        else
        cout<<i;
    }
    return 0;
}

int main(int argc, char* argv[ ])
{
    DWORD ThreadId;
    HANDLE ThreadHandle;
    int Param;

    cout<<"Enter a number:";
    cin>>Param;

    cout<<"Prime numbers less than and equal to your number \n"<<i;
    ThreadHandle=CreateThread(NULL,0,Prime,&Param,0,&ThreadId);

    waiter=WaitForMultipleObjects(MAX_THREADS,hThreads,TRUE,INFINITE);

    for(int i=0;i<MAX_THREADS;i++)
        CloseHandle(hThreads[i]);

    return 0;
}
