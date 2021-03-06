## Rearrange a linked list
Given a singly linked list, the task is to rearrange it in a way that all odd position nodes are together and all even positions node are together.
Assume the first element to be at position 1 followed by second element at position 2 and so on.
Note: You should place all odd positioned nodes first and then the even positioned ones. (considering 1 based indexing). Also, the relative order of odd positioned nodes and even positioned nodes should be maintained. [🔗Goto](https://practice.geeksforgeeks.org/problems/rearrange-a-linked-list/1/?page=8&difficulty[]=1&status[]=unsolved&sortBy=submissions#) 

<details>
<summary>Full Code</summary>

```java
import java.util.*;
import java.io.*;

class Node{
    int data;
    Node next;
    
    Node(int x){
        data = x;
        next = null;
    }
    
}
class GFG{
	static void printList(Node node) 
	{ 
		while (node != null) 
		{ 
			System.out.print(node.data + " "); 
			node = node.next; 
		} 
		System.out.println(); 
	}
    public static void main(String args[]) throws IOException { 
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while(t > 0){
        	int n = sc.nextInt();
            Node head = new Node(sc.nextInt());
            Node tail = head;
            for(int i=0; i<n-1; i++)
            {
                tail.next = new Node(sc.nextInt());
                tail = tail.next;
            }
            new Solution().rearrangeEvenOdd(head);
            printList(head); 
            t--;
        }
    } 
} 
// } Driver Code Ends


/*

class Node {

    int data;
    Node next;

    Node(int d) {
        data = d;
        next = null;
    }
}
This is method only submission.
You only need to complete the below method.
*/
class Solution
{

   // Should rearrange given linked list such that all even
   // positioned Nodes are before odd positioned.
   // Returns nothing
    void rearrangeEvenOdd(Node head)
    {
          //  The task is to complete this method
          Node odd=head;
          Node even=head.next;
          Node first=odd,second=even;
          while(odd!=null && even!=null){
              odd.next=even.next;
              
              if(odd.next==null){
                  break;
              }
              odd=odd.next;
              even.next=odd.next;
              even=even.next;
          }
          
          odd.next=second;
          head=first;
    }
}
```
</details>

```java
/*

class Node {

    int data;
    Node next;

    Node(int d) {
        data = d;
        next = null;
    }
}
This is method only submission.
You only need to complete the below method.
*/
class Solution
{

   // Should rearrange given linked list such that all even
   // positioned Nodes are before odd positioned.
   // Returns nothing
    void rearrangeEvenOdd(Node head)
    {
          //  The task is to complete this method
          Node odd=head;
          Node even=head.next;
          Node first=odd,second=even;
          while(odd!=null && even!=null){
              odd.next=even.next;
              
              if(odd.next==null){
                  break;
              }
              odd=odd.next;
              even.next=odd.next;
              even=even.next;
          }
          
          odd.next=second;
          head=first;
    }
}
```