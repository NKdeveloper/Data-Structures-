

import java.io.*;
import java.util.*;
import java.util.Random;
 

/**
 * This class creates the values of the tree, inserts them into the tree, balances and prints the tree
 * @author Nikhil Kanamarla
 * @version 1.8
 */
public class BSTTest
{
 

    // determines the number of layers 
    static int depth;
 

    // @param de is a method variable to represent depth 
    public static void setdepth(int de) {
        depth = de;
    }
 

    public static void main(String args[]) {
 

        // sets up BST object to use methods in BST class
        // sets up arraylist to store values for balancing method
 

        System.out.println("it works for 1,000 values");
 

        BST<Integer> add = new BST<Integer>();
 

        ArrayList <Integer> values = new ArrayList <Integer>();
 

        // creates values and inserts them into binary search tree and arraylist
 

        for (int i = 0; i < 1000; i++) {
 

            int random = (int)(Math.random() * 100 + 1);
 

            add.insert(random);
            values.add(random);
        }
        // sorts and prints out arraylist
        Collections.sort(values); 
        System.out.println(values);
 

        // balances tree
        add.balance(values,depth);
 

    
    }
}
