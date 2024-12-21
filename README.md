# MY-ATM
//Create ATM machine using java
<br><br>
package Shiv;<br>
import java.util.*;
class ATMmachine{
 int Pin=1993;
 float Balance=10000;
 public void checkpin(){
     System.out.println("Enter you pin Number");
     Scanner sc =new Scanner(System.in);
     int Enteredpin = sc.nextInt();
     if(Enteredpin==Pin){
         menu();
     
     }
     else{
         System.out.println("Enter a valid pin");
     }
 }
     public void menu(){
         System.out.println("Enter Your choice--");
         System.out.println("1,Check Account Balance");
         System.out.println("2,Cash Deposite");
         System.out.println("3,Cash Withdraw");
         System.out.println("4,Exit");
         Scanner sc=new Scanner(System.in);
         int opt=sc.nextInt();
         
         if(opt==1){
             CheckBalance();
             
         }
         else if(opt==2){
             CashDeposite();
         }
         else if(opt==3){
             CashWithdraw();
         }
         else if(opt==4){
             return;
         }
         else 
     {
         System.out.println("Enter a valid choice");
     }
 }
 public void  CheckBalance(){
     System.out.println("Your Available Balance is -:"+Balance);
	      
 }
 public void CashWithdraw(){
     System.out.println("Enter the Withdrwal Ammount");
     Scanner sc = new Scanner(System.in);
     float amount = sc.nextFloat();
     if(amount>Balance){
         System.out.println("Insufficient Balance");
     }
     else{
         Balance = Balance-amount;
         System.out.println("Money withdrawal Successfull ");
         System.out.println("Your Current Amount -:"+Balance);
         menu();
     }
 }
 public void CashDeposite(){
     System.out.println("Enter the amount");
     Scanner sc = new Scanner(System.in);
     float amount = sc.nextFloat();
     Balance=Balance+amount;
     System.out.println("Money Deposited Successfully -:"+Balance);
     
 }
 
}
class MainATM {
 public static void main(String[] args) {
     ATMmachine obj= new ATMmachine();
     obj.checkpin();
     
 }
}
