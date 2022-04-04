# C-program
Placement series program
#include<iostream>
using namespace std;
int fact(int n)
{
    if(n==0)
    {
        return 1;
    }
    return n*fact(n-1);
}
int main()
{
    int n=5;
    int ans =fact(n);
    cout<<ans;
}

---------------------------------------------------------------------------------------------

#include<iostream>
using namespace std;

    int power(int n)
    {
        //base case
        if(n==0)
            return 1;
    // recursion relation
    int smallerProblem = power(n-1);
    int biggerProblem = 2*smallerProblem;
    return biggerProblem;
    }
int main()
{
    int n;
    cin>>n;
    int ans = power(n);
    cout<<ans<<endl;
}

-------------------------------------------------------------------------------------------------------------------

#include<iostream>
using namespace std;
void num(int n)
{
    if(n==0)
    {
        return ;
    }
    cout<<n<<" ";
    num(n-1);
}
int main()
{
    int n;
    cin>>n;
    num(n);
}

---------------------------------------------------------------------------------------------------------------------------------//

#include<iostream>
using namespace std;

void reachHome(int src,int dest)
{
    cout<<"sorce"<<src<<" destination "<<dest<<endl;
    // base case
    if(src == dest)
    {
        cout<<" pahuch gya"<<endl;
        return ;
    }
    //processing - ek step aage badhjao
    src++;

    // recursive call
    reachHome(src,dest);
}
int main()
{
    int dest = 10;
    int src = 1;
    cout<<endl;
    reachHome(src,dest);
}

----------------------------------------------------------------------------------------------------------------//

#include<iostream>
using namespace std;
int fibbo(int n)
{
   if(n==0)
   {
       return 0;
   }
   if(n==1)
   {
       return 1;
   }
    int x = fibbo(n-1) + fibbo(n-2);
    return x;
}
int main()
{
    int n = 8;
    cout<<fibbo(n);
}

-----------------------------------------------------------------------------------------------------
#include<iostream>
using namespace std;

int climb(int n)
{
    if(n==0)
    {
        return 1;
    }
    if(n<0)
    {
        return 0;
    }
    int ans = climb(n-1) + climb(n-2);
    return ans;
}
int main()
{
    int n;
    cin>>n;
    cout<<climb(n);
}

-----------------------------------------------------------------------------------------
#include<iostream>
using namespace std;
void saydigit(int n,string arr[])
{
    
    if(n==0)
    {
        return ;
    }
    int digit = n%10;
    n = n/10;
    
    // recursive call
    saydigit(n,arr);
    cout<<arr[digit];
}
int main()
{
    string arr[10] = {"zero","one","two","three","four","five","six","seven","eight","nine"};
    int n;
    cin>>n;
    cout<<endl<<endl<<endl;
  
    saydigit(n,arr);
    cout<<endl<<endl<<endl;
    
}

--------------------------------------------------------------------------------------------------------------------

#include<iostream>
using namespace std;
bool issort(int *arr,int n)
{
    // base case
    if(n==0 || n==1)
    {
        return true;
    }
    if(arr[0]>arr[1])
    {
        return false;
    }
    else
    {
        // recursive call
        bool remainingarray = issort(arr+1,n-1);
        return remainingarray;
    }
}
int main()
{
    int arr[5] = {1,2,3,4,5};
    int n = 5;
   
    bool ans = issort(arr,n);
    if(ans)
    {
        cout<<"array is sorted";
    }
    else{
        cout<<"array is not sorted";
    }

}
#include<iostream>
using namespace std;
int sum(int *arr,int n)
{
    // base case
    if(n==0)
    {
        return 0;
    }
    if(n==1)
    {
        return arr[0];
    }
    int remainingpart = sum(arr+1,n-1);
    int temp = arr[0]+remainingpart;
    return temp;

}
int main()
{
    int arr[5] = {3,2,5,1,6};
    int n= 5;
    int asn = sum(arr,n);
    cout<<asn;

}

------------------------------------------------------------------------------------------------------------------------------------//
find element usingn recursion
#include<iostream>
using namespace std;

void print(int *arr,int n)
{
    cout<<"size of array is "<<endl;
    for(int i=0;i<n;i++)
    {
        cout<<arr[i]<<" ";

    }
    cout<<endl;
}
bool findelement(int *arr,int n,int k)
{
    // base case
    print(arr,n);
    if(n==0)
    {
        return false;
    }
    if(arr[0]==k)
    {
        return true;
    }
    else
    {
    bool remainder = findelement(arr+1,n-1,k);
    return remainder;
    }


}
int main()
{
    int arr[5] = {1,2,4,6,3};
    int n=5;
    int key;
    cin>>key;
    int temp = findelement(arr,n,key);
    
    if(temp)
    {
        cout<<"found element";
    }
    else
    {
        cout<<"Not found element";
    }

}

-------------------------------------------------------------------------------------------------------
Binary search

#include<iostream>
using namespace std;

// cheack conditon
void print(int arr[],int s,int e)
{
    for(int i=s;i<=e;i++)
    {
        cout<<arr[i]<<" ";
    }
    cout<<endl;
}

bool binarysearch(int *arr,int s,int e,int key)
{
    cout<<endl;
    print(arr,s,e);
    //base case
    //element not found
    if(s>e)
    {
        return false;
    }
      int mid = s +(e-s)/2;
      cout<<"value of the mid "<<mid<<endl;
    // element found
    if(arr[mid]==key)
    {
        return true;
    }
  // recursive call
    if(arr[mid]<key)
    {
        binarysearch(arr,mid+1,e,key);
    }
    else{
        return binarysearch(arr,s,mid-1,key);
    }

}
int main()
{
    int arr[5] = {1,2,3,4,5};
    int n=5;
    int key;
    cin>>key;
   
    int ans = binarysearch(arr,0,5,key);
    if(ans)
    {
        cout<<"find";
    }
    else
    {
        cout<<"not find";
    }

}

----------------------------------------------------------------------------------------------------------------------------//
Reverse String using recursion

#include<iostream>
using namespace std;

void reverse(string &str,int i,int j)
{
    cout<<"Call recieved for "<<str<<endl;
    // base case
    if(i>j)
    {
        return ;
    }
    swap(str[i],str[j]);
    i++;
    j--;
    // recursive call
    reverse(str,i,j);
}
int main()
{
    string name = "Shubham";

    reverse(name,0,name.length()-1 );
    cout<<name<<endl;
}

--------------------------------------------------------------------------------------------------------------------------

check pallindrom

#include<iostream>
using namespace std;

bool pallindrome(string &str,int i,int j)
{
    if(i>j)
    {
        return true;
    }
    if(str[i]!=str[j])
    {
        return false;
    }
    else
    {
        // recursive call
        return pallindrome(str,i+1,j-1);

    }
}
int main()
{
   string name = "MOM";
   cout<<endl;
   bool ispallindrome = pallindrome(name,0,name.length()-1);
   if(ispallindrome)
   {
       cout<<"Is pallindrome"<<endl;
   }
   else{
       cout<<"Not pallindrome"<<endl;
   }

}


-------------------------------------------------------------------------
change power
a=2,b = 3;
a**3;

#include<iostream>
using namespace std;

int power(int a,int b)
{
    if(a==0)
    {
        return 1;
    }
    if(b==1)
    {
        return a;
    }
    // recursive call
    int ans = power(a,b/2);
    // if b is even
    if(b%2==0)
    {
        return ans*ans;
    }
    else
    {
        // if is odd
        return a*ans*ans;
    }
}
int main()
{
    int a,b;
    cin>>a>>b;
    int ans = power(a,b);
    cout<<"Answer is "<<ans<<endl;



}

-------------------------------------------------------------//
bubble sort

#include<iostream>
using namespace std;
void sortArray(int *arr,int n)
{
    // base case=already sorted
    if(n==0 || n==1)
    {
        return ;
    }
    for(int i=0;i<n-1;i++)
    {
        if(arr[i]>arr[i+1])
        {
            swap(arr[i],arr[i+1]);
        }
    }
    // Recursive call
    sortArray(arr,n-1);
}
int main()
{
    int arr[5] = {2,5,1,6,9};
    sortArray(arr,5);
    for(int i=0;i<5;i++)
    {
        cout<<arr[i];
    }
}

---------------------------------------------------------------------------------------------------//

Merge Sort

#include<iostream>
using namespace std;

void merge(int *arr,int s,int e)
{
    int mid = (s+e)/2;
    int len1 = mid-s+1;
    int len2 = e-mid;
    int *first = new int[len1];
    int *second = new int[len2];
    // copy values
    int mainArrayIndex = s;
    for(int i=0;i<len1;i++)
    {
        first[i] = arr[mainArrayIndex++];
    }
    mainArrayIndex = mid+1;
    for(int i=0;i<len2;i++)
    {
        second[i] = arr[mainArrayIndex++];
    }
    // merge 2 sorted arrays
    int index1 = 0;
    int index2 = 0;
    mainArrayIndex = s;
    while (index1<len1 && index2 <len2)
    {
        
            if(first[index1]<second[index2])
            {
                arr[mainArrayIndex++] = first[index1++];
            }
            else{
                arr[mainArrayIndex++] = second[index2++];
            }

    }
        while (index1<len1)
        {
            arr[mainArrayIndex++] = first[index1++];

        }
        while (index2<len2)
        {
            arr[mainArrayIndex++] = second[index2++];
        }
        
    }

    
void mergeSort(int *arr,int s,int e)
{
    // base case
    if(s>=e)
    {
        return;
    }
    int mid = (s+e)/2;
    // left part sort karna hai
    mergeSort(arr,s,mid);

    // right part sort karna hai
    mergeSort(arr,mid+1,e);
    // merge
    merge(arr,s,e);
}
int main()
{
    int arr[11] = {3,7,0,1,2,8,2,3,6,2,9};
    int n = 11;
    mergeSort(arr,0,n-1);
    for(int i=0;i<n;i++)
    {
        cout<<arr[i]<<" ";
      
    }
    cout<<endl;
    return 0;
}
