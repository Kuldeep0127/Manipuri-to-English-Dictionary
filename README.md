# Manipuri-to-English-Dictionary
from tkinter import *
from tkinter import messagebox

def clear():
    entry.config(state=NORMAL)
    entry.delete(0,END)
    textarea.delete(1.0,END)
    textarea.config(state= DISABLED)

def exit():
    res = messagebox.askyesno('Confirm','Do you want to exit?')
    if res== TRUE:
        root.destroy()
    else:
        pass
root = Tk()
root.geometry('800x626')
root.title('English To Manipuri dictionary')
bg = PhotoImage(file="greyy.png")
# create a canvas
my_canvas = Canvas(root, width=800, height=626)
my_canvas.pack(fill="both", expand=True)

# set an image in canvas
my_canvas.create_image(0,0,image=bg, anchor="nw")
root.resizable(1,1)

my_canvas.create_text(396,37, text="Translation Dictionary", font=("Garamond",48),fill='#ffffff')

my_canvas.create_text(380,131, text="Enter a word", font=("Roboto",30),fill='#ffffff')

entry = Entry(root, font=('castellar','15','bold'), bg='Whitesmoke', justify = CENTER,
              relief=GROOVE)
entry.place(x=220,y=160)
entry.focus_set()

searchimage = PhotoImage(file='searchh.png')
searchbutton= Button(root, image =searchimage, bd=2 , bg='#242424',activebackground='grey')
searchbutton.place(x=530,y=156)

my_canvas.create_text(385,350, text="Meaning", font=("Roboto",30),fill='#ffffff')

textarea = Text(root, font=('Castellar','11','bold'),width=33,height=4,bd=0,relief=GROOVE,wrap='word')
textarea.place(x=180,y=385)

exitimage = PhotoImage(file='exit.png')
exitbutton= Button(root, image =exitimage, bd=1, bg='#242424',activebackground='grey',command =exit)
exitbutton.place(x=350,y=490)

clearimage = PhotoImage(file='clear.png')
clearbutton= Button(root, image =clearimage, bd=3,bg="#242424", activebackground='grey',command=clear)
clearbutton.place(x=580,y=399)

root.mainloop()
