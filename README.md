# Caesercipher-programm
encryption and Decryption word 
package Caeserprogram;
import java.util.Scanner;
public class CaesarCipherMain {
	    public static final String alph = "abcdefghijklmnopqrstuvwxyz";
	    public static String encoding(String plainT, int shift) {
	        plainT = plainT.toLowerCase();
	        String cipherT = "";
	        for (int i = 0; i < plainT.length(); i++) {
	            int mappingV = alph.indexOf(plainT.charAt(i));
	            int enVal = (shift + mappingV) % 26;
	            char Val = alph.charAt(enVal);
	            cipherT = cipherT + Val;
	        }
	        return cipherT;
	    }
	    public static String decoding(String cipherT, int shift) {
	        cipherT = cipherT.toLowerCase();
	        String plainT = "";
	        for (int i = 0; i < cipherT.length(); i++) {
	            int mappingV = alph.indexOf(cipherT.charAt(i));
	            int deVal = (mappingV - shift) % 26;
	            if (deVal < 0)
	            {
	                deVal = alph.length() + deVal;
	            }
	            char Val = alph.charAt(deVal);
	            plainT = plainT + Val;
	        }
	        return plainT;
	    }
	 
	    public static void main(String[] args) {
	        Scanner scan = new Scanner(System.in);
	        System.out.println("SOLUTION PROGRAM : ");
	        System.out.println("ABIODUN TAOFEEK TIAMIYU : ");
	        System.out.println("STUDENT NUMBER: 21910091 : ");
	        System.out.println("OPERATING SYSTEM AND NETWORK SECURITY : ");
	        System.out.println("ASSIGNMENT 2 : ");
	        System.out.println("Enter the text message to be encrypted ");
	        String msg = new String();
	        msg = scan.next();
	        System.out.println(" Encrypted Text : " + encoding(msg, 4));
	        System.out.print(" Decryptd Text : ");
	        System.out.print(decoding(encoding(msg, 4), 4));
	        scan.close();
	    }
	}
