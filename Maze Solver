import java.util.Scanner;
import java.io.*;
import java.util.*;
import java.util.Stack;
import java.util.Queue;
/**
 * Solves a maze from the @ symbol to the $ symbol 
 * 
 * @author Nikhil Kanamarla 
 * @version 1.0
 */
public class MazeSolver 
{
    // arraylist and stack for x and y 
    static ArrayList<Integer> x2 = new ArrayList();
    static ArrayList<Integer> y2 = new ArrayList();
    
     static  Stack x = new Stack();
       static  Stack y = new Stack();
      
    // instance variables 
    static int checkDirection; 
    static int column;
    static int row;
    static int z;
    static int z2;
    static String storage;
    static String store;
    static String [] [] values;

    public static void main(String args []) {
        try {

            //scanner code that reads in from a file 
            Scanner scan;
            scan = new Scanner(new BufferedReader(new FileReader("maze.java")));
            
            // intializing variables 
            row = 0; 
            column = 0;
            checkDirection = 0;

            // findinng the number of rows and columns 
            while (scan.hasNextLine()) {

                store = scan.nextLine();

                row++;
            }
            column = store.length();

            scan.close();

            values = new String [row] [column];

            scan = new Scanner(new BufferedReader(new FileReader("maze.java")));

            String tempString = "";

            // puts the maze into a 2D array
            while (scan.hasNext()) {
                for (z = 0; z < row; z++){

                    if(scan.hasNextLine()) {
                        tempString = scan.nextLine();

                    }

                    for (z2 = 0; z2 < column; z2++){

                        values [z] [z2] = (tempString.substring(z2, z2+1));
                        System.out.println(values[z][z2]);

                    }
                }
            }
            scan.close();

            
            // Finds the start symbol 
            int r = 0;
            int c = 0;
            
            for (r = 0; r < row; r++){
                for (c = 0; c < column; c++){
                    if( (values [r] [c]).equals("@")){
                        System.out.println(" the column is " + c + " " +  "the row is " + r);
                        pushcoordinate(r,c);
                    }
                }

            }


        }catch (Exception e) {
            System.out.println("Error" + e.getMessage());
            e.printStackTrace();
            System.exit(0);
        }
    }
    
    //@param contains the coordinates of x and y
    
    public static void pushcoordinate(int y1, int x1) {
        // y1 is row, x1 is column 
        // adds to linked list
        x2.add(x1);
        y2.add(y1);

        // prints out all psotions 
        System.out.println(" the column is " + x1 + " " +  "the row is " + y1);

        // prints out final coordinates 
        if((values [y1] [x1]).equals("$")) {

            x.addAll(x2);
            y.addAll(y2);
            System.out.println(Arrays.toString(x.toArray()));
            System.out.println(Arrays.toString(y.toArray()));

            System.exit(0);

        }
        
        // replaces old postions with wall
        values [y1] [x1] = ("#"); 

        // checks for paths in all directions 
        checkAll(y1,x1);

    }

    
    //@param contains the coordinates of x and y
    
    public static void checkAll(int y1, int x1) {
        storage = " ";

        // check up
        if(y1 > 0 && y1 <= row) {
            storage = values [(y1-1)] [x1];
        }

        if(storage.equals((".")) || storage.equals ("$")) {

            pushcoordinate((y1-1),x1);  
            checkDirection = 1;
        }

        //check down
        if(y1 <= row) {
            storage  = values [y1+1] [x1];

        }

        if(storage.equals((".")) || storage.equals ("$")) {
            pushcoordinate((y1+1),x1);  
            checkDirection = 2;
        }

        //check left
        if (x1 > 0){
            storage  = values [y1] [x1-1];
        }

        if(storage.equals((".")) || storage.equals ("$")) {
            pushcoordinate((y1),x1-1);  
            checkDirection = 3;
        }

        // check right
        if (x1 < column){
            storage = values [y1] [x1+1];
        }    

        if(storage.equals((".")) || storage.equals ("$")) {
            pushcoordinate((y1),x1+1);  
            checkDirection = 4;
        } else {
            
            // if stuck, go bacwards in the direction the program came from 
            x2.remove(0);
            y2.remove(0);

            if (checkDirection == 1 ) {
                values [y1+1] [x1] = ("."); 
                checkAll(y1+1,x1);
            }
            if (checkDirection == 2 ) {
                values [y1-1] [x1] = ("."); 
                checkAll(y1-1,x1);
            }
            if (checkDirection == 3 ) {
                values [y1] [x1+1] = ("."); 
                checkAll(y1,x1+1);
            }
            if (checkDirection == 4 ) {
                values [y1] [x1-1] = ("."); 
                checkAll(y1,x1-1);
            }

        }

    }

}



public class Node
{
    int value;
    static Node next;
    static Node top;
    

    public Node(int v) {
        value = v;
    }

    public int getValue() { //gets value of node
        return value;
    }
    public void setValue(int v) { // picks valus of nodes
        value = v;
    }
    public Node getNext() { //moves to new nodes
        return next;
    }
    public void setNext(Node n) { //creates new nodes 
        next = n;
    }
      public void push(Node n) {
        n.setNext(top);
        top = n;
      
    }
    
    public Node pop() {
        if (top == null) {
            return null;
        }
        Node ret = top;
        top = top.getNext();
        ret.setNext(null);
        return ret;
    }
    
    public Node peek() {
        return top;
    }
    
     public boolean isEmpty() {
        return next == null;
    }
    public int size() {
        return value;
    }
}
