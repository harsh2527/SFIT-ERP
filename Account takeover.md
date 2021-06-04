## How I Hacked My College :-)

Vulnerability- No limit of incorrect attempts

 ### Summary

It is possible to brute-force recovery code from email on SFIT-ERP as it doesn’t have an incorrect input limit. I have tried 80+ different combinations until I reached the 6 code user received on email.  
   
### Severity — Medium

## Steps to Reproduce:-  

```
1. Click “Reset password” option on the erp portal.
```
![](https://cdn-images-1.medium.com/max/720/1*aPTSDVivsckZnGhuBlLz5Q.png)

 ``` 
2.Enter “PID and email(Email can be found from the online payment portal just by entering the PID ([www.sfit.ac.in/SfitPaymentLandPageById.php)](http://www.sfit.ac.in/SfitPaymentLandPageById.php%29))".
```
![](https://cdn-images-1.medium.com/max/720/1*1uTXhswB6WHdQLMe0BD8KQ.png)

![](https://cdn-images-1.medium.com/max/720/1*ZWvmrg8o49uRZjq92if5oA.jpeg)

The page where one can find the email required to send a reset request. 

```
3. Start burpsuit and capture the request.  
```
```
4. click “check for existence” it will land you on the page where OTP needs to be added.
```
  

![](https://cdn-images-1.medium.com/max/720/1*3Ubk8iPeWSXHH9JRB6g6-g.jpeg)
```
5. Send the captured request and sent it to intruder.
```
![](https://cdn-images-1.medium.com/max/720/1*fpk4exXEn0bHyI5-PBs-DQ.png)

```
6. From intruder launch brute-force for the 6 digit code.
```
![](https://cdn-images-1.medium.com/max/720/1*ochmjcHBEJ2cFfpAOcKMng.png)

if we observe carefully we the length value remains constant for all the pages since it redirects to incorrect OTP but if the OTP is correct then a different page shall load modifying the length value so at the instance length changes we hit a jackpot.

![](https://cdn-images-1.medium.com/max/720/1*quTIS073owFi9fyxRPYyjQ.png)

Now we have the correct OTP and we can reset the user password! 

  

## Proof of Concept

[https://www.youtube.com/watch?v=z0OqZptW8tk](https://www.youtube.com/watch?v=z0OqZptW8tk)  
 

### Mitigation  
   
Limit quantity of attempts to enter recovery code  
   
### Impact  
   
Account takeover


Found by
Harsh Malhotra 

Contact for any query📧 email - harshmalhotra@protonmail.com
