import os
from datetime import datetime
import mysql.connector as myconn
from colorama import Fore, Style, init
init(autoreset=True)
mydb = myconn.connect(
    host="localhost",      
    user="root",          
    password="115061",  
    database="bank"       
)
mydb1 = mydb.cursor()
# function 1
def getname(n99):
    mydb1.execute("select name from customer where atmno = %s",(n99,))
    datax= mydb1.fetchone()
    return datax

#function 2
def getphone(n99):
    mydb1.execute("select phoneno from customer where atmno = %s",(n99,))
    datax= mydb1.fetchone()
    return datax



#function 3
def getatmno(n99):
    mydb1.execute("select atmno from customer where atmno = %s",(n99,))
    datax= mydb1.fetchone()
    return datax

#function 4
def getamount(n99):
    mydb1.execute("select totalamount from customer where atmno = %s",(n99,))
    datax= mydb1.fetchone()
    return datax


def getpass(n99):
    mydb1.execute("select pass from customer where atmno = %s",(n99,))
    datax= mydb1.fetchone()
    return datax

def update(n97,n98,n99):
    mydb1.execute(f"update customer set {n97} = %s where atmno =%s",(n98,n99,))
    mydb.commit()
    


#function 5
def getstr(syn1):
    return str(input(Fore.WHITE + f"please! enter  {syn1}: "))
def getint(syn1):
    return int(input(Fore.WHITE + f"please! enter  {syn1} :  "))
def getfloat(syn1):
    return float(input(Fore.WHITE + f"please! enter {syn1}:   "))
def getpassi(syn1):
    return int(input(Fore.WHITE + f"please! enter  {syn1} :  "))


    
    
while(1):
    print()
    print()
    print()
    print(Fore.BLUE + Style.BRIGHT + "WELCOME TO BMS")
    print(Fore.BLUE + "******************************************************************")
    print(Fore.BLUE + "******************************************************************")
    print(Fore.YELLOW + "1. open account")
    print(Fore.YELLOW + "2. transfer money")
    print(Fore.YELLOW + "3. check balance")
    print(Fore.YELLOW + "4. change detail")
    print(Fore.YELLOW + "5. delete account")
    print(" ")
    option1 = int(input(Fore.WHITE + "enter your choice: "))
    os.system('cls') 
    print()

    # condition 1
    if(option1==1):
        cname = getstr("name")
        print()
        cnumber = getint("mobile number")
        catmno = str(int(cnumber/2)) + str(sum(ord(i) for i in cname))
        print()
        camount = getfloat("the amount you want to deposit")
        print()
        cpass = getpassi(" a strong password(integer(suggestion 4 digit))")
        print()
        os.system('cls') 

        while(1):
            ctemp1 = getpassi("your password again")

            if(cpass == ctemp1):
                mydb1.execute("insert into customer(name,atmno,totalamount,pass,phoneno) values (%s,%s,%s,%s,%s)",
                              (cname, catmno, camount, cpass,cnumber))
                mydb.commit()
                

                os.system('cls') 
                print(Fore.GREEN + "Thanks to be our customer.if any query please contact to bank manager.")
                print("have a good day") 
                print()
                print(Fore.WHITE + "**********************************")
                print(Fore.GREEN + "* Your account no is:   ",catmno,"        Your password is: ",cpass)
                print(Fore.WHITE + "**********************************")
                break
                print()
            else:
                print()
                print(Fore.RED + "Wrong password, enter again")
                continue
            print()  
        print()
        print()
        print()
        print()
        print(Fore.YELLOW + "1. to go to home page.")
        print(Fore.YELLOW + "2. to know your account detail")
        print()
        option2 = int(input(Fore.WHITE + "enter your option: "))
        os.system('cls') 
        if(option2==1):
            continue
        elif(option2==2):
            print()
            print(Fore.GREEN + f"Customer Name: {cname}")
            print(Fore.GREEN + f"Mobile no: {cnumber}")
            print(Fore.GREEN + f"Account no: {catmno}")
            print(Fore.GREEN + f"Account no: {cnumber}")
        else:
            print()
            print(Fore.RED + "wrong key.")
            continue
        continue

    # condition 2
    elif(option1 == 2):
        townno=getint("your account number")
        data1=getatmno(townno)
        if(data1):
            while(1):
                print()
                tatmno = getint("enter reciver account number")
                
                data2=getatmno(tatmno)
                if(data2):
                    print()
                    v2=1
                    while(v2==1):
                        tamount=getfloat(f" the amount to send to ")
                        amountpresent1=getamount(townno)
                        amountpresent1=amountpresent1[0]
                        
                        if(amountpresent1 >= tamount):
                            v2=0
                            print()
                            v5=3
                            while(v5>0):
                                
                                tpass=getpassi("your password ")
                                pass1=getpass(townno)
                                pass1=pass1[0]
                                
                                if(pass1==tpass):
                                    v5=0
                                    print()
                                    
                                    mydb1.execute("update customer set totalamount = %s where atmno =%s",(float(amountpresent1)-tamount, townno))
                                    mydb.commit()
                                    amountpresent2=getamount(townno)
                                    amountpresent2 = amountpresent2[0]
                                    mydb1.execute("update customer set totalamount= %s where atmno = %s",(float(amountpresent2) + tamount, tatmno))
                                    mydb.commit()
                                    print()
                                    os.system('cls') 
                                    print(Fore.LIGHTGREEN_EX+"Amount transfer sucessfull from ",townno)
                                    print(Fore.GREEN + f"now your amount is: {float(amountpresent1)-tamount}")
                                    print()
                                    
                                    
                                else:
                                    os.system('cls') 
                                    print()
                                    print(Fore.RED + "You entered wrong password...")
                                    print(Fore.RED + f" {v5-1} tries available.")
                                    v5=v5-1
                        else:
                            os.system('cls') 
                            print(Fore.RED + "Your balance is lower than this amount... enter again...")
                            print()
                    break
                else:
                    os.system('cls') 
                    print()
                    print(Fore.RED + "This account not available... enter another account no...")
                    print() 
                    continue  
        else:
            os.system('cls') 
            print()
            print(Fore.RED + "Account not found")
            
        continue

    # condition 3
    elif(option1==3):
        print()
        cbalance=getint("youur account number")
        mydb1.execute("select totalamount from customer where atmno =%s",(cbalance,))
        nowamount = mydb1.fetchone()
        if(nowamount):
            v6=3
            while(v6>0):
                cpass=getpassi("your password")
                mydb1.execute("select pass from customer where atmno = %s",(cbalance,))
                pass3=mydb1.fetchone()
                pass3=pass3[0]
                if(pass3==cpass):
                    nowamount=nowamount[0]
                    print()
                    os.system('cls') 
                    print(Fore.GREEN + f"Your balance is: {nowamount}")
                    v6=0
                else:
                    print()
                    os.system('cls') 
                    print(Fore.RED + "Wrong password...")
                    print(Fore.RED + f"{v6-1} tries available..")
                    v6=v6-1
        else:
            os.system('cls') 
            print()
            print(Fore.RED + "You entered wrong account number....")
        continue

    # condition 4
    elif(option1==4):
       
        v13=2
        while(v13>0):
            uatmno=getint("your account number")
            data4=getatmno(uatmno)
            if(data4):
                v13=0  
                v12=3
                while(v12>0):
                    upass=getpassi("your password")
                    data5=getpass(uatmno)
                    data5=data5[0]
                    
                    if(upass==data5):
                        v12=0
                        os.system('cls') 
                        list1=["0. if not any to change","1. name","2. phone no","3. change password"]
                        v8=3
                        list2=[]
                        list3=[]
                        
                        while(v8):
                            os.system('cls') 
                            for v9 in list1:
                                if(v9 in list2):
                                    continue
                                else:
                                    print(v9)
                                    
                            data3=int(input("enter options: "))
                            list2.append(list1[data3])
                            if(data3==0):
                                os.system('cls') 
                                break
                            list3.append(data3)

                            v8-=1
                        os.system('cls') 
                        print("updating your details....")
                        for v10 in list3:
                            if(v10==1):
                                uname=str(input("enter your new name: "))
                                update("name",uname,uatmno)
                            elif(v10==2):
                                uphone= int(input("enter your new phone number: "))
                                update("phoneno",uphone,uatmno)
                            elif(v10==3):
                                unewpass=int(input("enter new paaword(integer): "))
                                update("pass",unewpass,uatmno)
                            elif(v10==0):
                                continue
                            else:
                                break
                            print()
                            
                            print("sucessfully updated")
                    else:
                        v12=v12-1
                        os.system('cls') 
                        print("your password is wrong")
                        print(f"only {v12} try left")
                        
            else:
                os.system('cls') 
                print("accounr not found")
                v13=v13-1
                print(f"only {v13} try left")
               

            







    elif(option1==5):
        print()
        os.system('cls') 
        datmno=getint("your account number")
        print()
        mydb1.execute("select pass from customer where atmno =%s",(datmno,))
        pass4=mydb1.fetchone()
        if(pass4):
            pass4=pass4[0]
            v7=3
            while(v7>0):
                dpass=getpassi("your password")
                if(dpass==pass4):
                    v7=0
                    mydb1.execute("delete from customer where atmno =%s",(datmno,))
                    mydb.commit()
                    os.system('cls') 
                    print()
                    print(Fore.GREEN + "Your account has been deleted successfully.you can give your feedback")
                else:
                    print()
                    os.system('cls') 
                    print(Fore.RED + "You entered wrong password...")
                    print(Fore.RED + f"{v7-1} tries available.")
                    v7=v7-1
        else:
            print()
            os.system('cls') 
            print(Fore.RED + "You do not have any account..")




















    
    else:
        print(Fore.RED + "You entered wrong key")

