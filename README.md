# algorithms
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.tsa;

/**
 *
 * @author dhaim
 */
public class TSA {
    
    
    //function for the ternary search 
    static int ternarySearch(int begin, int end, int key, int arr[]){
       
        if(end >= begin){
        // find mid1 and mid2
        int mid1 = begin + (end - begin)/3;
        int mid2 = end - (end - begin)/3;
         if (arr[mid1] == key) {
                return mid1;
            }
            if (arr[mid2] == key) {
                return mid2;
            }
            
             if (key < arr[mid1]) {
 
                // The key lies in between l and mid1
                return ternarySearch(begin, mid1 - 1, key, arr);
            }
            else if (key > arr[mid2]) {
 
                // The key lies in between mid2 and the end
                return ternarySearch(mid2 + 1, end, key, arr);
            }
            else {
 
                // The key lies in between mid1 and mid2
                return ternarySearch(mid1 + 1, mid2 - 1, key, arr);
            }
        }
        
    return -1;
    }

    public static void main(String[] args) {
        int begin, end, p, key;
 
        // Get the array
        // Sort the array if not sorted
        int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
 
        // Starting index
        begin = 0;
 
        // end element index
        end = 9;
 
        // Checking for 5
 
        // Key to be searched in the array
        key = 5;
 
        // Search the key using ternarySearch
        p = ternarySearch(begin, end, key, arr);
 
        // Print the result
        System.out.println("Index of " + key + " is " + p);
 
        // Checking for 50
 
        // Key to be searched in the array
        key =10;
 
        // Search the key using ternarySearch
        p = ternarySearch(begin, end, key, arr);
 
        // Print the result
        System.out.println("Index of " + key + " is " + p);
    }
}
    
