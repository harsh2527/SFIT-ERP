
Vulnerability- No limit of incorrect attempts 

Summary  

It is possible to brute-force recovery code from email on SFIT-ERP as it doesn't have an incorrect input limit. I have tried 80+ different combinations until I reached the 6 code user received on email.  
   
Severity - Medium   

Steps to Reproduce:-  

1.  Click "Reset password" option on the erp portal(sfiterp.sfit.co.in:98/reset\_password.asp).  

2. Enter "PID and email(Email can be found from the online payment portal just by entering the PID (www.sfit.ac.in/SfitPaymentLandPageById.php))".  

3. Start burpsuit and capture the request.  

4.  click "check for existence" it will land you on the page where OTP needs to be added.  

5.  Send the captured request and sent it to intruder.  

6.  From intruder launch brute-force for the 6 digit code.  
 


Proof of Concept 


https://www.youtube.com/watch?v=z0OqZptW8tk (Video only visible via link )  
   
  
Mitigation  
   
Limit quantity of attempts to enter recovery code  
   
Impact  
   
Account takeover

  
Found by

Harsh Malhotra 

Contact details for any query:-

email - harshmalhotra257@gmail.com
