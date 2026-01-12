Capgemini Questions 

Problem Statement –

You have write a function that accepts, a string which length is “len”, the string has some “#”, in it 
you have to move all the hashes to the front of the string and return the whole string back and print it.

char* moveHash(char str[],int n);

Example :

Sample Test Case

Input:

Move#Hash#to#Front

Output:

###MoveHashtoFront

```

class Main {
    public static void main(String[] args) {
        String str = "Move#Hash#to#Front";
        /*Why mention stringbuilder length while creating itself?..
         Becoz..while stringbuilder is resizing internally
it creates a another char array if first char array with size of 16 characters get exceeded..
the new array's size would be oldArraySize*2+2...
so in this small program it might not important but in large programs it is important*/
        
        StringBuilder str2 = new StringBuilder(str.length());
        
        for(char i:str.toCharArray()) {
            if(i=='#') {
                str2.append(i);
            }
        }
        
        for(int i=0;i<str.length();i++) {
            if(str.charAt(i)!='#') {
                str2.append(str.charAt(i));
            }
        }
        
        String str1 = str2.toString();
        System.out.println(str1);
    }
}

```

Problem Statement –

Capgemini in its online written test have a coding question, wherein the students are given a string with multiple characters that are repeated consecutively. You’re supposed to reduce the size of this string using mathematical logic given as in the example below :

Input :

aabbbbeeeeffggg

Output:

a2b4e4f2g3

Input :

abbccccc

Output:

ab2c5

without using HashMap

```
class Main {
    public static void main(String[] args) {
        String str = "abb";
        int count = 1;
        StringBuilder str1 = new StringBuilder();
        char prev = str.charAt(0);

       // Adding the first element in the result string
        str1.append(prev);
        
        // Edge Case --> if(str.length()==0) return -1;
        
        for(int i=1;i<str.length();i++) {
            char curr = str.charAt(i);
                if(curr==prev)
                    count++;
                else if(curr!=prev) {
                  str1.append(count);
                  str1.append(curr);
                  count  = 1;
                }
            prev = curr;
        }

        // Adding the last element's count in the return string
        str1.append(count);
        System.out.println(str1);
    }
}

```

Problem Statement: Sunset View (West Side)

You are given an array of integers where each integer represents the height of a 
building arranged in a straight line from west to east.
The sunset is in the west, which corresponds to the left side of the array.
A building can see the sunset if all the buildings to its west (left side) are shorter than it.
Your task is to determine how many buildings can see the sunset.

Input:
arr = {3, 4, 4, 5, 2, 3}
Output:
3

```
class Main {
    public static void main(String[] args) {
        int arr[] = {3,4,4,5,2,3};
        int max = Integer.MIN_VALUE;
        int count = 0;
        
        for(int i=0;i<arr.length;i++) {
            if(arr[i]>max) {
                max = arr[i];
                count++;
            }
        }
        System.out.println(count);
    }
}
```
