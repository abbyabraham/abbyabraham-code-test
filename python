# Line of Credit Code Sample
# by Abby Abraham

# At the top are the required variables. Credit Limit and APR are harded coded here. 
limit=5000
apr=0.365
dailyinterest = apr/365
bal = limit
apr_read = apr * 100
interestSum = []
#Class to create transactions
class Transaction:
   def __init__(self, amt, bal):
      self.amt = amt
      self.bal = bal   
   def pay(self):#pay to the account
      remain = self.bal + self.amt	
      return remain
   def buy(self):#withdraw funds
      remain = self.bal - self.amt	
      return remain
print("\n")
print "Your CREDIT limit is: $" , limit
print "Your INTEREST rate is: " , apr_read, "%"
print("\n")
print ('Buy Something, Make a Payment, or Continue to the Next Day')
#the program generates inputs for withdraw and payment for the 30 day payment period
for x in range(0, 30):
   day_no=x+1
   print 'Day', day_no, ': '
   print "Your Balance is: ", bal 
   v1 = 2
   while v1 !=1:
      
       v2 = 2
       choice=str(raw_input('Type (B) to buy, (P) for payment, (C) to continue or (Q) to quit:'))
       if choice == 'B' or choice=='b':
           while v2 !=1:
	     transamt=""
	     try:  
	       transamt = int(raw_input("Buy Something: How much would you like? $")) #Number is required
	     except ValueError:
		print "Not a Number. Try again."
             if transamt<>"":    
                 if transamt > bal: #Makes sure user doesn't withdraw over the limit
	             print("Too much. Try again,")
	         else:                 
		     t = Transaction(transamt, bal)
	             bal = t.buy() 
	             v2=1
	             print "Transaction accepted! Your new balance is $", bal
       	      
                   
       elif choice == 'P' or choice=='p':
           while v2 !=1:
	       transamt=""
               try:  
	          transamt = int(raw_input("Payment: How much would you like to pay? $"))
	       except ValueError:
		  print "Not a Number. Try again"
               if transamt<>"": 
	           if limit < transamt + bal:#Makes sure user doesn't pay over the limit
	               print("Too much. Try again.")
	           else:	       
		       t = Transaction(transamt, bal)
	               bal = t.pay()
                       v2=1
	               print "Payment accepted! Your new balance is $", bal
	       
       elif choice == 'C' or choice=='c':
	   dailyBal=limit-bal #appends each end of day interest totals in a list
	   a=dailyBal*dailyinterest 	
	   interestSum.append(a)
           v1=1
       elif choice == 'Q' or choice=='q':
           quit()
       else:
          print "Not a valid response. Try again"
def listsum(numList):
    theSum = 0
    for i in numList:
        theSum = theSum + i
    return theSum
final=listsum(interestSum)
F=limit-bal
S=F+final #tallies up the list of end of day interest totals
print("\n")
 
W='{0:.2f}'.format(S)
print("You've reached the end of the payment cycle.") 
raw_input("Press Enter to see your monthly payment...")
print("\n")
print "Payment Due: $", W
print("\n")
#Thanks!!
