from tkinter import *
import random
import time;

root=Tk()
root.geometry("1600x800+0+0")
root.title("Restaurant Management System")

Tops = Frame(root, width = 1600, height=50,bg="Green",relief=SUNKEN)
Tops.pack(side=TOP)

f1 = Frame(root, width = 800, height=700,  relief=SUNKEN)
f1.pack(side=LEFT)
f2 = Frame(root, width = 800, height=700, bg="powder blue", relief=SUNKEN)
f2.pack(side=RIGHT)

localtime = time.asctime(time.localtime(time.time()))
label1 = Label(Tops, font=('arial',50,'bold'),text="Restaurant Management System",fg='Steel Blue',bd=10,anchor='w')
label1.grid(row=0,column=0)
label2 = Label(Tops, font=('arial',20,'bold'),text=localtime,fg='Steel Blue',bd=10,anchor='w')
label2.grid(row=1,column=0)
#---------------------------------------------CALCULATOR--------------------------------------------------------------------------------------
def onclick(numbers):
    global operator
    operator += str(numbers)
    text_input.set(operator)

def onclear():
    global operator
    operator = ""
    text_input.set(operator)

def onequals():
    global operator
    val=str(eval(operator))
    text_input.set(val)
    operator=""

operator=""
text_input = StringVar()

txtDisplay = Entry(f2,font=('arial',20,'bold'), textvariable=text_input,bd=30,insertwidth=4,bg='powder blue',justify='right').grid(columnspan=4)

b7 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="7",bg="Steel Blue",command=lambda:onclick(7)).grid(row=2,column=2)
b8 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="8",bg="Steel Blue",command=lambda:onclick(8)).grid(row=2,column=1)
b9 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="9",bg="Steel Blue",command=lambda:onclick(9)).grid(row=2,column=0)
badd = Button(f2,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),text="+",bg="Red",command=lambda:onclick("+")).grid(row=2,column=3)

b6 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="6",bg="Steel Blue",command=lambda:onclick(6)).grid(row=3,column=0)
b5 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="5",bg="Steel Blue",command=lambda:onclick(5)).grid(row=3,column=1)
b4 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="4",bg="Steel Blue",command=lambda:onclick(4)).grid(row=3,column=2)
bsub = Button(f2,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),text="-",bg="Red",command=lambda:onclick("-")).grid(row=3,column=3)

b3 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="3",bg="Steel Blue",command=lambda:onclick(3)).grid(row=4,column=0)
b2 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="2",bg="Steel Blue",command=lambda:onclick(2)).grid(row=4,column=1)
b1 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="1",bg="Steel Blue",command=lambda:onclick(1)).grid(row=4,column=2)
bmul = Button(f2,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),text="*",bg="Red",command=lambda:onclick("*")).grid(row=4,column=3)

b0 = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="0",bg="Steel Blue",command=lambda:onclick(0)).grid(row=5,column=0)
bc = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="C",bg="Steel Blue",command=onclear).grid(row=5,column=1)
beq = Button(f2,padx=16,pady=16,bd=8,fg="white",font=('arial',20,'bold'),text="=",bg="Steel Blue",command=onequals).grid(row=5,column=2)
bdiv = Button(f2,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),text="/",bg="Red",command=lambda:onclick("/")).grid(row=5,column=3)
#------------------------------------------ITEM-LISTS-----------------------------------------------------------------------------
rand = StringVar()
Fries = StringVar()
Pizza = StringVar()
Burger = StringVar()
SubTotal = StringVar()
Total = StringVar()
Paneer = StringVar()
Drinks = StringVar()
Tax = StringVar()
Ice_Cream = StringVar()
Chicken_Wings = StringVar()
Chilli_Potato = StringVar()

#------------------------------------------FIRST COLUMN----------------------------------------------------------------------------
lblreference = Label(f1,font=('comic sans',16,'bold'),text="Reference",bd=16, anchor='w')
lblreference.grid(row=0,column=0)
txtreference = Entry(f1,font=('comic sans',16,'bold'),textvariable=rand,bd=10,insertwidth=4, bg="Silver",justify='right')
txtreference.grid(row=0,column=1)

lblfries = Label(f1,font=('comic sans',16,'bold'),text="Fries",bd=16, anchor='w')
lblfries.grid(row=1,column=0)
txtfries = Entry(f1,font=('comic sans',16,'bold'),textvariable=Fries,bd=10,insertwidth=4, bg="Silver",justify='right')
txtfries.grid(row=1,column=1)

lblpizza = Label(f1,font=('comic sans',16,'bold'),text="Pizza",bd=16, anchor='w')
lblpizza.grid(row=2,column=0)
txtpizza = Entry(f1,font=('comic sans',16,'bold'),textvariable=Pizza,bd=10,insertwidth=4, bg="Silver",justify='right')
txtpizza.grid(row=2,column=1)

lblburger = Label(f1,font=('comic sans',16,'bold'),text="Burger",bd=16, anchor='w')
lblburger.grid(row=3,column=0)
txtburger = Entry(f1,font=('comic sans',16,'bold'),textvariable=Burger,bd=10,insertwidth=4, bg="Silver",justify='right')
txtburger.grid(row=3,column=1)

lblwings = Label(f1,font=('comic sans',16,'bold'),text="Hot Chicken Wings",bd=16, anchor='w')
lblwings.grid(row=4,column=0)
txtwings = Entry(f1,font=('comic sans',16,'bold'),textvariable=Chicken_Wings,bd=10,insertwidth=4, bg="Silver",justify='right')
txtwings.grid(row=4,column=1)

lblpotato = Label(f1,font=('comic sans',16,'bold'),text="Honey Chilli Potato",bd=16, anchor='w')
lblpotato.grid(row=5,column=0)
txtpotato = Entry(f1,font=('comic sans',16,'bold'),textvariable=Chilli_Potato,bd=10,insertwidth=4, bg="Silver",justify='right')
txtpotato.grid(row=5,column=1)
#------------------------------------------SECOND COLUMN-----------------------------------------------------------------------------
lbldrinks = Label(f1,font=('comic sans',16,'bold'),text="Drinks",bd=16, anchor='w')
lbldrinks.grid(row=0,column=2)
txtdrinks = Entry(f1,font=('comic sans',16,'bold'),textvariable=Drinks,bd=10,insertwidth=4, bg="Silver",justify='right')
txtdrinks.grid(row=0,column=3)

lblservice = Label(f1,font=('comic sans',16,'bold'),text="Paneer Tikka",bd=16, anchor='w')
lblservice.grid(row=2,column=2)
txtservice = Entry(f1,font=('comic sans',16,'bold'),textvariable=Paneer,bd=10,insertwidth=4, bg="Silver",justify='right')
txtservice.grid(row=2,column=3)

lbltax = Label(f1,font=('comic sans',16,'bold'),text="GST",bd=16, anchor='w')
lbltax.grid(row=3,column=2)
txttax = Entry(f1,font=('comic sans',16,'bold'),textvariable=Tax,bd=10,insertwidth=4, bg="Silver",justify='right')
txttax.grid(row=3,column=3)

lblice = Label(f1,font=('comic sans',16,'bold'),text="Ice Cream",bd=16, anchor='w')
lblice.grid(row=1,column=2)
txtice = Entry(f1,font=('comic sans',16,'bold'),textvariable=Ice_Cream,bd=10,insertwidth=4, bg="Silver",justify='right')
txtice.grid(row=1,column=3)

lblsubtotal = Label(f1,font=('comic sans',16,'bold'),text="Sub Total",bd=16, anchor='w')
lblsubtotal.grid(row=4,column=2)
txtsubtotal = Entry(f1,font=('comic sans',16,'bold'),textvariable=SubTotal,bd=10,insertwidth=4, bg="Silver",justify='right')
txtsubtotal.grid(row=4,column=3)

lbltotal = Label(f1,font=('comic sans',16,'bold'),text="Total Cost",bd=16, anchor='w')
lbltotal.grid(row=5,column=2)
txttotal = Entry(f1,font=('comic sans',16,'bold'),textvariable=Total,bd=10,insertwidth=4, bg="Silver",justify='right')
txttotal.grid(row=5,column=3)

#--------------------------------------------BUTTON----------------------------------------------------------------------------------
def stop():
    root.destroy()

def Reset():
    rand.set("")
    Fries.set("")
    Pizza.set("")
    Burger.set("")
    SubTotal.set("")
    Total.set("")
    Paneer.set("")
    Drinks.set("")
    Tax.set("")
    Ice_Cream.set("")
    Chicken_Wings.set("")
    Chilli_Potato.set("")   

def Cal_Total():    
    x = random.randint(1,1000)
    randomRef = str(x)
    rand.set(randomRef)
    
    COF = float(Fries.get())
    COP = float(Pizza.get())   
    COB = float(Burger.get())
    COD = float(Drinks.get())
    COIC = float(Ice_Cream.get())
    COW = float(Chicken_Wings.get())
    COCP = float(Chilli_Potato.get())
    COPNR = float(Paneer.get())   

    COF = COF * 50
    COP = COP * 120   
    COB = COB * 30
    COD = COD * 200
    COIC = COIC * 60
    COW = COW * 100
    COCP = COCP * 70
    COPNR = COPNR * 80    

    total_Tax = ((COF + COP + COB + COD + COIC + COW + COCP + COPNR) * 0.05)
    total_cost = (COF + COP + COB + COD + COIC + COW + COCP + COPNR)
    overall = (total_Tax + total_cost)
    Tax.set(total_Tax)
    SubTotal.set(total_cost)
    Total.set(overall)
    
btnReset = Button(f1,padx=16,pady=8,bd=16,fg="Black",font=('arial',16,'bold'),width=10,text="RESET",bg="Pink",command=Reset).grid(row=7,column=1)    
btnTotal = Button(f1,padx=16,pady=8,bd=16,fg="Black",font=('arial',16,'bold'),width=10,text="TOTAL",bg="Pink",command=Cal_Total).grid(row=7,column=2)
btnStop = Button(f1,padx=16,pady=8,bd=16,fg="Black",font=('arial',16,'bold'),width=10,text="CLOSE",bg="Pink",command=stop).grid(row=7,column=3)

root.mainloop()