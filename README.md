// Isomorphic string
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        String str1=scan.next();
        String str2=scan.next();
        char freq1[]=new char[256];
        char freq2[]=new char[256];
        if(str1.length()!=str2.length()){
            System.out.print("no");
            return;
        }
        for(int i=0;i<str1.length();i++){
            char ch1=str1.charAt(i);
            char ch2=str2.charAt(i);
            if(freq1[ch1]==0 && freq2[ch2]==0){
                freq1[ch1]=ch2;
                freq2[ch2]=ch1;
            }else{
                if(freq1[ch1]!=ch2 || freq2[ch2]!=ch1){
                    System.out.print("no");
                    return;
                }
            }
        }
        System.out.print("yes");
    }
}

// Camel case conversion
import java.util.*;
public class Main {
    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        String str=scan.nextLine();
        char[] ch=str.toCharArray();
        StringBuilder sb=new StringBuilder();
        StringBuilder con=new StringBuilder();
        int n=str.length();
        for(int i=0;i<n;i++){
            if(ch[i]!=' '){
                sb.append(ch[i]);
            }else{
                //change(sb);
                con.append(change(sb));
                sb.setLength(0);
            }
        }
        //change(sb);
        con.append(change(sb));
        System.out.print(con);
    }
    public static StringBuilder change(StringBuilder sb){
        StringBuilder s=new StringBuilder();
        char[] arr=sb.toString().toCharArray();
        for(int i=0;i<arr.length;i++){
            if(i==0){
                s.append(Character.toUpperCase(arr[i]));
            }else{
                s.append(arr[i]);
            }
        }
        return s;
    }
}
