/**
 * Description: Reads two numbers from a file, stores them into a double linked list
 * Description: Adds the two numbers and prints out the results
 * 
 * @author Nikhil Kanamarla 
 * @version 1.6
 */

import java.io.*;
import java.util.Scanner;

public class InfiniteAdder
{

    public static void main(String [] args) {
        try {
            // important variables
            int total;
            int totalcarry = 0;
            int total2 = 0;

            // sets up scanner to read the integers from the file
            Scanner scan;
            scan = new Scanner(new BufferedReader(new FileReader("num1.txt")));
            scan.useDelimiter(",");

            Scanner scan2;
            scan2 = new Scanner(new BufferedReader(new FileReader("num2.txt")));
            scan2.useDelimiter(",");
            
            // sets up double linked list
            NodeResources head = new NodeResources((scan.nextInt())); 
            NodeResources current = head;
            NodeResources prev; 
            NodeResources head2 = new NodeResources((scan2.nextInt())); 
            NodeResources current2 = head2;
            NodeResources prev2; 
            
            
            // reads integers from file
            while(scan.hasNext()) {
                current.setNext(new NodeResources((scan.nextInt())));
                prev = current;
                current = current.getNext();
                current.setPrev(prev);

            }

            while(scan2.hasNext()) {
                current2.setNext(new NodeResources((scan2.nextInt())));
                prev2 = current2;
                current2 = current2.getNext();
                current2.setPrev(prev2);
            }
            
            // used to add the two numbers
            total = ((current.getNodeResources() + current2.getNodeResources()) + total2); 
            
            // moves current to the beginning of linked list
            current = head;
            current2 = head2;
            
            // linked list to print sum backward 
            NodeResources head3 = new NodeResources(total);
            NodeResources current3 = head3;
            NodeResources prev3; 

            
            while(current.getNext() != null) {
                while(current2.getNext() != null) { 

                    // used to add the two numbers
                    total = ((current.getNodeResources() + current2.getNodeResources()) + total2); 

                    // moves to next nodes
                    current = current.getNext();
                    current2 = current2.getNext();
                    
                    // used to print out numbers and carry over integers
                    // used to create the final linked list
                    if(total >= 10 ) {
                        totalcarry = total - 10;  
                        System.out.print(totalcarry);
                        total2 = 1;
                        current3.setNext(new NodeResources((totalcarry)));
                        prev3 = current3;
                        current3 = current3.getNext();
                        current3.setPrev(prev3);
                    }  else   {
                        System.out.print(total);
                        total2 = 0;
                        current3.setNext(new NodeResources((total)));
                        prev3 = current3;
                        current3 = current3.getNext();
                        current3.setPrev(prev3);
                    }
                }
            }
            
            // prints out total and is used to create the final node
            total = ((current.getNodeResources() + current2.getNodeResources()) + total2); 
            System.out.println(total);
            current3.setNext(new NodeResources((total)));
            prev3 = current3;
            current3 = current3.getNext();
            current3.setPrev(prev3);
            
            // prints out numbers in correct order 
            while(current3.getPrev()!= null ) {
                System.out.print(current3.getNodeResources());
                current3 = current3.getPrev();
            }
        }
        // Checks for exceptions when the code is run and returns the error 
        catch (Exception e) {
            System.out.println("Error" + e.getMessage());
            e.printStackTrace();
            System.exit(0);
        }
    }
}


  * Write a description of class NodeResources here.		
  * 		
  * @author (your name) 		
  * @version (a version number or a date)		
  */		
 public class NodeResources extends InfiniteAdder		
 {		
     // important variable used in methods below 		
     int NodeResources;		
 		
     // Helps setup nodes		
     NodeResources next;		
     NodeResources prev;		
     		
     // setter method sets up linked list 		
     //@param integer d means the value of variable above 		
     public NodeResources (int d) { 		
         NodeResources = d;		
     }		
     		
     //@return getter method sends value of node		
        public int getNodeResources() {		
         return NodeResources;		
     }		
     		
     //@param integer d means the value variable above		
     // setter method sets values of nodes		
        public void setNodeResources(int d) {		
         NodeResources = d;		
     }		
 		
      // getter method moves to new node		
      //@return sends next node 		
        public NodeResources getNext() {		
         return next;		
    }		
 		
     //@param means NodeResources which helps setup new node		
     // setter method sets new node value		
        public void setNext(NodeResources d) {		
         next = d;		
     }		
     		
      // getter method moves to previous nodes		
      //@return sends last node		
        public NodeResources getPrev() {		
         return prev;		
     }		
 		
      // setter method sets previous node value		
        public void setPrev(NodeResources d) {		
         prev = d;		
     }		
 }

