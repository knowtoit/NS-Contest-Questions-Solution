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
