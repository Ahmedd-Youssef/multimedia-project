---
## This Porgram Convert Text-To-Voice
### Using Tkinter in Python
---
```python
from tkinter import *
from tkinter import ttk, messagebox
import pyttsx3
engine = pyttsx3.init()

root = Tk()
root.geometry("600x600")
root.title("MULTIMEDIA PROJECT")
root.config(bg="antiquewhite2")

def Text_To_Speach():
     text = textbox.get()
     if text:
         engine.say(text) 
         engine.runAndWait()
     else: 
         messagebox.showerror("Input Error", "Please Enter Text To Convert To Speech.")

def Delete_Text():
     textbox.delete(0, END)

def enter_key(event):
     Text_To_Speach()


Label(root, text="Text To Speach", font=("Impact", 35,"bold"), bg="antiquewhite2").pack(pady=10)
Label(root, text="Click Enter Or Play To Listen Your Text", font=("Helvetica", 20, "bold"), bg="antiquewhite2").pack(pady=10)
Label(root, text="Enter Your Text", font=("Helvetica", 20, "bold"), bg="antiquewhite2").pack(pady=10)

textbox = Entry(root, width=50)
textbox.pack(pady=20)
textbox.bind("<Return>", enter_key)

button_frame = Frame(root, bg="antiquewhite2")
button_frame.pack(pady=40)

Button(button_frame, text="Play",font=("Helvetica", 10, "bold"), padx=20, pady=10, bg="lightblue",  command=Text_To_Speach).pack(side=LEFT, padx=15)
Button(button_frame, text="Set" ,font=("Helvetica", 10, "bold"), padx=20, pady=10, bg="lightgreen", command=Delete_Text).pack(side=LEFT, padx=15)
Button(button_frame, text="Exit",font=("Helvetica", 10, "bold"), padx=20, pady=10, bg="lightcoral", command=root.quit).pack(side=LEFT, padx=15)

root.mainloop()
