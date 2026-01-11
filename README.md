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
