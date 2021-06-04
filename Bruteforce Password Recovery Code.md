### Summary 
It is possible to bruteforce recovery code from email on SFIT-erp as it dosen't have incorrect input limt. I have tried 80+ different combinations until i reached the 6 code user received on email. 
````
Steps to Reproduce:- 
1.  Click "Reset password" option on the erp portal(sfiterp.sfit.co.in:98/reset_password.asp).
2. Enter "PID and email(Email can be found from the online payment portal just by enterning the pid (www.sfit.ac.in/SfitPaymentLandPageById.php))".
3. Start burpsuit and capture the request.
4.  click "check for existance" it will land you to the page where otp needs to be added.
5.  Send the captured request and sent to intruder.
6.  From intruder lauch bruteforce for the 6 digit code.
````
### Proof of Concept Video
````
https://www.youtube.com/watch?v=z0OqZptW8tk (Video only visible via link )
````

### Mitigation 
````
Limit quantity of attempts to enter recovery code 
````
### Impact 
````
Account takeover
````
