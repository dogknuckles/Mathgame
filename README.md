# Mathgame
from tkinter import *

plus = [3, 4, 5];
minus = [2,4,8] ;
times = [2,4,5] ;
start = [3,5,6]
#generate a random number for the answer boxes
import random
#answerrandom = random.randint(1, 10)

name=input("What is your name? ")

def quit():
    window.destroy()

    
def next () :
    window.destroy()
    global window
    global tkinter
    global canvas
    window = Tk()
    window.title("level 2!")
    Button(window, text="Quit",  width=10, command=quit).pack()
    Button(window, text="Next",  width=10, command=next).pack()
    canvas = Canvas(window, width= 650, height=500, bg = 'light blue')

def main():
    global window
    global tkinter
    global canvas
    window = Tk()
    window.title("Welcome to my maths game!")
    Button(window, text="Quit",  width=10, command=quit).pack()
    Button(window, text="Next",  width=10, command=next).pack()
    canvas = Canvas(window, width= 650, height=500, bg = 'light blue')

#add users name
    canvas.create_text(70, 430,  text='name' ,font="Ariel 15")
    canvas.create_rectangle(30, 490, 350, 440, fill="#E6CCFF", outline="black", width="3")
    canvas.create_text(90, 465,  text=name ,font="Ariel 20")    
#create the 'machine' shape       
#rectangles
    canvas.create_rectangle(140, 35, 280, 85, fill="#d21a1a", outline="black", width="3")
    canvas.create_rectangle(280, 35, 330, 175, fill="#e7841e", outline="black", width="3")
    canvas.create_text(305, 102,  text='+' ,font="Ariel 30  bold")
#adding text on top of the rectangles
    canvas.create_rectangle(125, 228, 280, 177, fill="#28d022", outline="black", width="3")
    canvas.create_text(202, 202,  text="-",font="Ariel 30  bold")
    canvas.create_rectangle(77, 180, 123, 350, fill="#226bd0", outline="black", width="3")
    canvas.create_text(100, 280,  text="x",font="Ariel 25  bold")
    canvas.create_rectangle(125, 345, 280, 395, fill="#d41160", outline="black", width="3")
    canvas.create_text(202, 370, text="=",font="Ariel 30  bold")
    
#ovals w/ text
    canvas.create_oval(260, 150, 350, 240, fill="#e7df1e", outline="black", width="3")
    canvas.create_text(305, 195,  text= plus[0] ,font="Ariel 25  bold")
    canvas.create_oval(145, 150, 55, 240, fill="#22bad0", outline="black", width="3")
    canvas.create_text(100, 195,  text="?" ,font="Ariel 30  bold")
    canvas.create_oval(145, 320, 55, 410, fill="#8222c5", outline="black", width="3")
    canvas.create_text(100, 365, text= minus[0] ,font="Ariel 25  bold")
#start
    canvas.create_oval(20, 20, 100, 100, fill="#E6CCFF", outline="black", width="3")        
    canvas.create_text(60, 60,  text=start[0] ,font="Ariel 30  bold")
#end
    canvas.create_oval(320, 320, 410, 410, fill="#E6CCFF", outline="black", width="3")
    canvas.create_text(365, 365,  text=((start[0]+plus[0])-minus[0])*times[0],font="Ariel 30  bold")
#answer boxes
    canvas.create_rectangle(450, 35, 600, 105, fill="#e7841e", activefill='white', outline="#d21a1a", width="5")
    canvas.create_text(525, 70,  text=random.randint(1, 10) ,font="Ariel 30  bold")
    
    canvas.create_rectangle(450, 140, 600, 210, fill="#226bd0", activefill='white', outline="#3e19b6", width="5")
    canvas.create_text(525, 175,  text=random.randint(1, 10) ,font="Ariel 30  bold")
    
    canvas.create_rectangle(450, 245, 600, 315, fill="#e7841e", activefill='white', outline="#d21a1a", width="5")
    canvas.create_text(525, 280,  text=((start[0]+plus[0])-minus[0])*times[0] ,font="Ariel 30  bold")
    
    canvas.create_rectangle(450, 360, 600, 430, fill="#226bd0", activefill='white', outline="#3e19b6", width="5")
    canvas.create_text(525, 395,  text=random.randint(1, 10) ,font="Ariel 30  bold") 
 
    
    canvas.pack()
    window.mainloop()
    
main()

