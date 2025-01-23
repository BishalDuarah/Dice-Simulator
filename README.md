# Dice-Simulator
import tkinter as tk
from PIL import Image, ImageTk
import random

window = tk.Tk()
window.geometry("500x360")
window.title("Dice Roll")

dice = ["dice 1.png","dice 2.png","dice 3.png","dice 4.png","dice 5.png","dice 6.png"]
image1 = ImageTk.PhotoImage(Image.open(random.choice(dice)))
image2 = ImageTk.PhotoImage(Image.open(random.choice(dice)))

label1 = tk.Label(window,image=image1)
label2 = tk.Label(window,image=image2)

label1.image = image1
label2.image = image2

label1.place(x=70, y=100)
label2.place(x=300,y=100)

def dice_roll():
    image1 = ImageTk.PhotoImage(Image.open(random.choice(dice)))
    label1.configure(image = image1)
    label1.image = image1

    image2 = ImageTk.PhotoImage(Image.open(random.choice(dice)))
    label2.configure(image = image2)
    label2.image = image2

button = tk.Button(window,text="Roll Dice",bg="green",fg="white",font = "Times 18 bold",command=dice_roll)
button.place(x = 200,y = 0)
window.mainloop()
