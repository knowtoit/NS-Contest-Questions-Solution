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
