---------
-----------
---------
# NS-Contest-Questions-Solution
- Repo for Contest Solution 
---------
------
--------
--------
--------
 ## Choose Card optimally(Contest)
  ## Link : https://my.newtonschool.co/playground/code/ow8g99l0yxno/
 ## Code : 
 ````
```

 import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
      Scanner sc = new Scanner(System.in);
      int numMAruti = sc.nextInt();
      int numShubahm = sc.nextInt();
      int [] cardsMaruti = new int [numMAruti];
      for(int i =0;i<numMAruti;i++)
      {
      cardsMaruti[i] = sc.nextInt();
    }
    int [] cardShubham = new int[numShubahm];
    for(int i =0;i<numShubahm;i++)
    {
        cardShubham[i] = sc.nextInt();
    }
    boolean marutiTurn = true;
    int maxPLayed = Integer.MIN_VALUE;
    while(numMAruti > 0 && numShubahm > 0)
    {
        if(marutiTurn)
        {
            int maxMaruti = Integer.MIN_VALUE;
            for( int i =0;i<numMAruti ;i++)
            {
                if(cardsMaruti[i] > maxPLayed && cardsMaruti[i] > maxMaruti)
                {
                    maxMaruti = cardsMaruti[i];
                }
            }
            if(maxMaruti > maxPLayed)
            {
                maxPLayed = maxMaruti;
                marutiTurn = false;
            }
            else {
                System.out.print("Shubham");
                return;
            }
        }
        else {
            int maxShubham = Integer.MIN_VALUE;
            for(int i =0;i<numShubahm;i++)
            {
                if(cardShubham[i] > maxPLayed && cardShubham[i] > maxShubham)
                {
                    maxShubham = cardShubham[i];
                }
            }
            if(maxShubham> maxPLayed)
            {
                maxPLayed = maxShubham;
                marutiTurn = true;
            }
            else{
                System.out.println("Maruti");
                return;
            }
        }
    }
}
}
```
````

------------------
------------------
------------------
## Permutation 1
## Link: https://my.newtonschool.co/playground/code/x69xe6mvla3v/
## Code:

```
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) throws IOException {
        BufferedReader br  = new BufferedReader(new InputStreamReader(System.in));
        int t = 1;
        while(t-->0){
            String S = br.readLine().trim();
            solution obj = new solution();
            List<String> ans = obj.find_permutation(S);
            for(int i=0; i<ans.size(); i++){
                System.out.print(ans.get(i)+" ");
            }
            System.out.println();
        }

             // Your code here
    }
}

class solution{
    public List<String> find_permutation(String S){

        List<String> arr = new ArrayList<>();
        printPerm(0, S.length()-1, S, arr);
        HashSet<String> h1 = new HashSet<>(arr);
        List<String> arr1 = new ArrayList<>(h1);
        Collections.sort(arr1);
        return arr1;
    }
    public static void printPerm(int l, int r, String S, List<String > arr){
        if(l==r){
            arr.add(S);
            return;
        }
        for(int i=l; i<=r; i++){
            S = swap(S.toCharArray(), l, i);
            printPerm(l+1, r, S, arr);
            S = swap(S.toCharArray(), l, i);
        }
    }
    public static String swap(char[] strArr, int i, int j){
        char temp = strArr[i];
        strArr[i] = strArr[j];
        strArr[j] = temp;
        return new String(strArr);
    }
}
```
Home Advantage
Link : https://my.newtonschool.co/playground/code/tji72sdv9zzw/
```
import java.io.*;

import java.util.*;
public class Main {
    private static int upper_bound(Integer arr[],int n, int key)

    {

        int l=0,r=n-1;

        int ans=n;

        while(l<=r){

            int i=(l+r)/2;

            if(arr[i] > key){

                ans=i;

                r=i-1;

            }

            else l=i+1;

        }

        return ans;

    }

    

    public static void main(String[] args) {

        

        InputStream inputStream = System.in;

        OutputStream outputStream = System.out;

        InputReader in = new InputReader(inputStream);

        OutputWriter out = new OutputWriter(outputStream);

        

        int n=Integer.parseInt(in.next());

       

        Integer a[] = new Integer[n];

        Integer c[] = new Integer[n];

        for(int t=0;t<n;t++){

            a[t] = Integer.parseInt(in.next());

            c[t]=a[t];

        }

        Integer b[] = new Integer[n];

        for(int t=0;t<n;t++){

            b[t] = Integer.parseInt(in.next());

        }

        

        Arrays.sort(c);

        

        

        for(int i=0;i<n;i++){

            int x = upper_bound(c,n,a[i] + b[i]);

            x--;

            out.print(x+" ");

        }

       

        out.close();

    }



    

    static class InputReader {

        BufferedReader reader;

        StringTokenizer tokenizer;

        public InputReader(InputStream stream) {

            reader = new BufferedReader(new InputStreamReader(stream), 32768);

            tokenizer = null;

        }



        public String next() {

            while (tokenizer == null || !tokenizer.hasMoreTokens()) {

                try {

                    tokenizer = new StringTokenizer(reader.readLine());

                } catch (IOException e) {

                    throw new RuntimeException(e);

                }

            }

            return tokenizer.nextToken();

        }



        public int nextInt() {

            return Integer.parseInt(next());

        }



    }



    static class OutputWriter {

        private final PrintWriter writer;



        public OutputWriter(OutputStream outputStream) {

            writer = new PrintWriter(new BufferedWriter(new OutputStreamWriter(outputStream)));

        }



        public OutputWriter(Writer writer) {

            this.writer = new PrintWriter(writer);

        }



        public void print(Object... objects) {

            for (int i = 0; i < objects.length; i++) {

                if (i != 0) {

                    writer.print(' ');

                }

                writer.print(objects[i]);

            }

        }



        public void println(Object... objects) {

            print(objects);

            writer.println();

        }



        public void close() {

            writer.close();

        }



        public void println(int i) {

            writer.println(i);

        }



    }

}
```
-----------
-----------
-----------

## Counting Zeroes to Ones (Contest)
## Link : https://my.newtonschool.co/playground/code/ciayxn5s4p8l/
## Code : 
```
#include <bits/stdc++.h> // header file includes every Standard library
using namespace std;

int main() {
	// Your code here
    int n, q;
    cin>>n>>q;
    set<int> row,col;
    while(q--)
    {
        int i,j;
        cin>>i>>j;
        row.insert(i);
        col.insert(j);
        long ans=(n-row.size())*(n-col.size());
        cout<<ans<<" ";
    }
    return 0;
}
```
## Fruit Market (Contest)
## Link : https://my.newtonschool.co/playground/code/795x92vayq6n/
## Code : 
```
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
      Scanner sc = new Scanner(System.in);
      Long N = sc.nextLong();
      int M = sc.nextInt();
      int arr[] = new int[M];
      for(int i =0;i<M;i++){
          arr[i] = sc.nextInt();
      }
      Arrays.sort(arr);
      int count =0;
      for(int i =arr.length-1;i>=0;i--)
      {
          if(N>=0)
          {
              N -=arr[i];
              count++;
          }
      }
System.out.println(count);
    }
}
```
## integer suffix
## Link : https://my.newtonschool.co/playground/code/b7ver9lbw2z2/
## code : 

import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        // Your code here
        Scanner sc=new Scanner(System.in);
        int N=sc.nextInt();
        int arr[]=new int[N];
        for(int i=0;i<N;i++)
        arr[i]=sc.nextInt();
        int X=sc.nextInt();
        int count=0;
        
        String binOfX=Long.toString(X,2);
        String[] arrBinary=new String[N];
        for(int i=0;i<N;i++)
        arrBinary[i]=Integer.toString(arr[i],2);
        for(String bi : arrBinary)
        {
            if(bi.endsWith(binOfX)){
                count++;
            }
        }
 
        System.out.println(count);
    }
}
------------
Beautiful Permutation
 Link : https://my.newtonschool.co/playground/code/baf6onlobjfq/
```
import java.io.*;
import java.util.*;

class Main {
    public static void main (String[] args) {
                      Scanner sc = new Scanner(System.in);
                      int n = sc.nextInt();
                      if(n==1){
                          System.out.print("YES");
                      }else if(n <=3 ){
                          System.out.print("NO SOLUTION");
                      }else{
                        System.out.print("YES");
                      }
    }
}
```
Matrix Problem 
Link : [
](https://my.newtonschool.co/playground/code/6l5s7vp0v7ac/)
```
import java.io.*;
import java.util.*;



class Main {
	public static void main (String[] args)throws IOException {

					BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
                      String ar[] = br.readLine().split(" ");
                      int n = Integer.parseInt(ar[0]);
                      int k = Integer.parseInt(ar[1]);
					  int a[][] = new int[n][n];
					  int sum=0,one_c=0;
                      for(int i=0;i<n;i++)
                      {
                          String arr[] = br.readLine().split(" ");
						  sum=0;
                          for(int j=0;j<n;j++)
                          {
                             int value=Integer.parseInt(arr[j]);
							 if(value==1)
							 one_c++;
							 sum=sum+value;
							 a[i][j]=sum;
                          }
                      }
					  for(int j=0;j<n;j++)
					  {
						  sum=0;
                          for(int i=0;i<n;i++)
						  {
                            sum=sum+a[i][j];
							a[i][j]=sum;
						  }
					  }

					if(k>=one_c)
					  {

						  System.out.println(n);

					  }
					else {
						int ans = 1;
						for(int len=1;len<=n;len++)
						{
							boolean flag= false;
						for(int i=len;i<n;i++)
						{
							for(int j=len;j<n;j++)
							{
								if(j-i==0)
								{
                                  if(a[i][j]<=k)
								  {
									  ans = Math.max(ans,ans+1);
									  flag=true;
									  break;
								  }

								}
								else if(j>i)
								{
									if(i==ans)
									{
										if(a[i][j]-a[i][j-ans-1]<=k)
										{
											ans=Math.max(ans,ans+1);
											flag = true;
											break;
										}
									}
									else {
										if(a[i][j]-a[i][j-ans-1]-a[i-ans-1][j]+a[i-ans-1][j-ans-1] <=k)
                                         {
											 ans = Math.max(ans,ans+1);
											 flag=true;
											 break;
										 }
									}
								}
								 if(i>ans) {

									if(j==ans)
									{
										if(a[i][j]-a[i-ans-1][j]<=k)
										{
											ans=Math.max(ans,ans+1);
											flag = true;
											break;
										}
									}
									else {
										if(a[i][j]-a[i-ans-1][j]-a[i][j-ans-1]+a[i-ans-1][j-ans-1] <=k)
                                         {
											 ans = Math.max(ans,ans+1);
											 flag=true;
											 break;
										 }
									}

								}
							}
							if(flag==true) break;
						}
						if(flag==false) break;
					}
					System.out.println(ans);
				}

	}
}
```[
](https://my.newtonschool.co/playground/code/6l5s7vp0v7ac/)
-------------
------------
Assign Mice to Holes
Link : https://my.newtonschool.co/playground/code/e88c0tl3tomo/
```
for i in range(int(input())):
    N = int(input())
    arr = [int(i) for i in input().split()]
    arr1 = [int(i) for i in input().split()]
    arr.sort()
    arr1.sort()

    time = 0
    for i,j in zip(arr,arr1):
        x = abs(i-j)
        if x>time: time = x

    print(time)
```
----
Minimum number to make median X
Link : https://my.newtonschool.co/playground/code/9ufiodw4j9wk/
```
java

for i in range(int(input())):
	n,k=map(int,input().split())
	x=list(map(int,input().split()))
	count,large_count,small_count,small,large=0,0,0,-1,10000000
	for i in x:
		if i==k:
			count+=1
		if i>k:
			large_count+=1
			large=min(large,i)
		if i<k:
			small_count+=1
			small=max(small,i)
	ans=abs(large_count-small_count)
	if(count>0):
		if(count>=n/2):
			print(0)
		else:
			print(ans)
	elif(small_count==large_count):
		if((large+small)//2==k):
			print(0)
		else:
			print(1)
	elif(small_count==0 or large_count==0):
		print(n)
	else:
		t=2*k-small
		if(t==large):
			print(ans)
		elif(t<large):
			large_count+=1
			print(min(ans+1,abs(large_count-small_count)+1))
		elif(t>large):
			l=2*k-large
			if(l>small):
				small_count+=1
				print(min(ans+1,abs(large_count-small_count)+1))
			else:
				print(ans+1)
```
----
Integer Modification (contest)
Link : https://my.newtonschool.co/playground/code/ws9nzs8a6inm/
```
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
     public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int k = sc.nextInt();
        int[] a = new int[n];
        int ans = 0;
        Map<Integer, Integer> mp = new HashMap<>();
        
        for (int i = 0; i < n; i++) {
            a[i] = sc.nextInt();
            if (mp.containsKey(a[i])) {
                mp.put(a[i], mp.get(a[i]) + 1);
            } else {
                mp.put(a[i], 1);
            }
        }
        
        List<Integer> res = new ArrayList<>();
        
        for (Map.Entry<Integer, Integer> entry : mp.entrySet()) {
            res.add(entry.getValue());
        }
        
        Collections.sort(res, Collections.reverseOrder());
        
        while (res.size() > k) {
            ans += res.get(res.size() - 1);
            res.remove(res.size() - 1);
        }
        System.out.println(ans);
    }
}
```
