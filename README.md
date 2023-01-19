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

```
## Maximise Strength
## Link - https://my.newtonschool.co/playground/code/w20g3e9av6po/
## Code:-

#include <stdio.h> // header file for Standard Input Output
#include <stdlib.h> // header file for Standard Library
#include <bits/stdc++.h> // header file includes every Standard Library
using namespace std;
#define int long long

signed main() {
    int n, k;
    cin >> n >> k;
    vector<vector<int>> v(k);
    for(int i=0; i<n; i++)
    {
        int m;
        cin >> m;
        int rem = (i+1)%k;
        v[rem].push_back(m);
    }
    for(int i=0; i<k; i++)
    {
        sort(v[i].rbegin(), v[i].rend());
    }
    int ans = 0; 
    for(int i=0; i<k ; i++)
    {
        ans += v[i][0];
    }
    cout << ans;
    //Your code here
    // return 0;
}
```

```
## Number od distinct numbers
## Link: https://my.newtonschool.co/playground/code/0up41fdcbxxi/
## Code:

import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        for(int i=0; i<t; i++){
            int a = sc.nextInt();
            int b = sc.nextInt();
            HashSet<Integer> set = new HashSet<>();
            set.add(a);
            for(int j=0; j<b; j++){
                HashSet<Integer> tempSet = new HashSet<>(set);
                for(int k : tempSet){
                    set.add(k+3);
                    set.add(k-3);
                    set.add(k*2);
                }
            }
            System.out.println(set.size());
        }
        sc.close();
        // Your code here
    }
}
```

```
## Boundary Traversal of Matrix
## Link: https://my.newtonschool.co/playground/code/f1jgaf8upx72/
## code:
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);

        int t = sc.nextInt();
        while(t>0)
        {
            int n = sc.nextInt();
            int m = sc.nextInt();

            int[][] arr = new int[n][m];

            for(int i=0; i<n; i++){
                for(int j=0; j<m; j++){
                    arr[i][j] = sc.nextInt();
                }
            }

            if(n==1)
            {
                for(int i=0; i<m; i++){
                    System.out.print(arr[0][i]+" ");
                }
                // System.out.println(" ");
            }

            else if(m==1)
            {
                for(int i=0; i<n; i++){
                    System.out.print(arr[i][0]+" ");
                }
            }
            else{
                for(int i=0; i<m; i++){
                    System.out.print(arr[0][i]+" ");
                }

                for(int i=1; i<n; i++){
                    System.out.print(arr[i][m-1]+" ");
                }

                for(int i=m-2; i>=0; i--){
                    System.out.print(arr[n-1][i]+" ");
                }

                for(int i=n-2; i>0; i--){
                    System.out.print(arr[i][0]+" ");
                }
            }
            System.out.println(" ");    
            t--;        
        }
        // Your code here
    }
}
```

```
## Frequency Sort
## Link: https://my.newtonschool.co/playground/code/qf2fjssxodzr/
## Code:
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();

        while(t-->0){
            int n = sc.nextInt();
            int[] a = new int[n];
            Map<Integer, Integer> map = new LinkedHashMap<>();
            for(int i=0; i<n; i++){
                a[i] = sc.nextInt();
                if(map.containsKey(a[i])){
                    map.put(a[i], map.get(a[i])+1);
                }
                else{
                    map.put(a[i], 1);
                }
            }
            List<Integer> keys = new ArrayList<>(map.keySet());

            Collections.sort(keys, (x, y)->{
                if(map.get(x)!= map.get(y)){
                    return map.get(y)-map.get(x);
                }
                else{
                    return x-y;
                }
            });
            for(int key: keys){
                for(int i=0; i<map.get(key); i++){
                    System.out.print(key +" ");
                }
            }
            System.out.println();
        }
        // Your code here
    }
}
```

```
## Smaller elements
## Link: https://my.newtonschool.co/playground/code/7sumrzqnxvty/
## code:
static int smallerElements(int a[], int n, int k){
        int low = 0;
        int high = n-1;
        int index = -1;

        while(low <= high){
                int mid = low +(high-low)/2;
                if(a[mid] == k)
                {
                        index = mid;
                        low = mid+1;
                }
                else if(a[mid]>k)
                {
                        high = mid-1;
                }
                else{
                        low = mid+1;
                        index = mid;
                }
        }
        return (index+1);
        //Enter your code here
}
```

```
## Cookie Division (contest)
## Link: https://my.newtonschool.co/playground/code/bbuuwbtqbo56/
## code:
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        // int arr[] = new int[n];
        // for(int i=0; i<n; i++){
        //     arrr[i] = sc.nextInt();
        // }

        int total = 0;
        for(int i=0; i<n; i++){
            int a = sc.nextInt();
            total += a;
        }

        if(total % 2==0){
            System.out.println("YES");
        }
        else{
            System.out.print("NO");
        }
        // Your code here
    }
}
```
```
## Crazy Walk (contest)
## Link: https://my.newtonschool.co/playground/code/h59kulh1qfzl/
## code:
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);
        int m = sc.nextInt();
        int n = sc.nextInt();

        if(m%2 !=0 || n%2 !=0)
        System.out.print("YES");

        else
         System.out.print("NO");
        // Your code here
    }
}
```

```
## Season of love
## Link: https://my.newtonschool.co/playground/code/lvssn0009cgg/
## code:
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc= new Scanner(System.in);
        int n = sc.nextInt();

        int roses = (n/3) + ((n%3)==2? 1:0);

        System.out.print(roses);
        // Your code here
    }
}
```

```
## Max Sum Column
## Link: https://my.newtonschool.co/playground/code/x5dczugcp0oi/
## Code:
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);
        int m = sc.nextInt();
        int n = sc.nextInt();
        
        int[][] matrix =  new int[m][n];

        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){
                matrix[i][j] = sc.nextInt();
            }
        }

        int maxSum = Integer.MIN_VALUE;

        for(int j=0; j<n; j++){
            int sum = 0;
            for(int i=0; i<m; i++){
                sum += matrix[i][j];
            }
            maxSum = Math.max(maxSum, sum);
        }
        System.out.print(maxSum);
        // Your code here
    }
}
```
