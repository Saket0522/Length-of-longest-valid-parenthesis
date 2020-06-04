import java.util.*;
import java.lang.*;
import java.io.*;

class GFG
 { 
	public static void main (String[] args)
	 {
	     Scanner sc = new Scanner(System.in);
	     int n = sc.nextInt();
	     sc.nextLine();
	     while(n-->0)
	     {
	        String str = sc.nextLine();
	        int l = str.length();
	        Stack<Integer> stk = new Stack<>(); 
            stk.push(-1); 
            int result = 0; 
            for (int i=0; i<l; i++) 
            { 
                if (str.charAt(i) == '(') 
                    stk.push(i); 
                else 
                { 
                    stk.pop(); 
                    if (!stk.empty()) 
                        result = Math.max(result, i - stk.peek()); 
                    else
                        stk.push(i); 
                }
            }
	        System.out.println(result);
	     }
	 }
}
