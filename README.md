# python-project
from pycricbuzz import Cricbuzz
from tkinter import *


root=Tk()
root.title("live cricket score")


root.geometry("800x200")



c = Cricbuzz()
match = c.matches()

score = c.livescore(match[0]['id'])
commentary = c.commentary(match[0]['id'])
score_board = c.scorecard(match[0]['id'])
for a in score :
    print(a)
    for b in score[a] :
        print(b,':',score[a][b])

s=str(score_board)
k=s.replace(",","\n")

score1=Label(root,font=("time",15,"bold"),bg="white",text=k)
score1.grid(row=2,column=2,pady=25,padx=100)


root.mainloop()
