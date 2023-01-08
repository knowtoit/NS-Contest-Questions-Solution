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
## Teacher 
## Link : https://my.newtonschool.co/playground/code/s86st68fimfo/
## Code : 
```
import java.util.ArrayList;
import java.util.*;
import java.util.List;

class Student implements Comparable<Student> {
    int number;
    int count;

    public Student(int number, int count) {
        this.number = number;
        this.count = count;
    }

    @Override
    public int compareTo(Student other) {
        return this.count - other.count;
    }
}

public class Main {
    public static void main(String[] args) {
        // Number of students
       Scanner sc = new Scanner(System.in);
       int N = sc.nextInt();
       int [] records  = new int [N];
       for(int i =0;i<N;i++)
       {
           records[i] = sc.nextInt();
       }

        // Create a list of students
        List<Student> students = new ArrayList<>();
        for (int i = 0; i < N; i++) {
            students.add(new Student(i + 1, records[i]));
        }

        // Sort the list of students in ascending order based on the number of students present
        // when they entered the classroom
        Collections.sort(students);

        // Print the student numbers in the order in which the students entered the classroom
        for (Student student : students) {
            System.out.print(student.number+" ");
        }
    }
}
```
## Count duplicates 
## Link : https://my.newtonschool.co/playground/code/rcvh8m0du828/
## Code : 
```
import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed
class Main {
    public static void main (String[] args) {
        // Your code here
        //HashMap<Integer, Integer> hm=new HashMap<>();
        Scanner sc=new Scanner(System.in);
        int N=sc.nextInt();
        int[] arr=new int[N];
        int i=0;
        for(i=0;i<N;i++)
        {
            arr[i]=sc.nextInt();

        }
        HashMap<Integer, Integer> hm=new HashMap<>();
        for(i=0;i<N;i++)
        {
            if(hm.containsKey(arr[i])){
                Integer pre=hm.get(arr[i]);
                hm.put(arr[i], pre + 1);

            }
            else
            {
                hm.put(arr[i],1);
            }

        }
        for(Integer n : hm.keySet())
        {
            if(hm.get(n)>1)
            {
                System.out.println(n +" " + hm.get(n));
            }
        }
    }
}
```
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
