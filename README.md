from tkinter import Canvas, Tk, Frame
from math import cos, sin 
from random import randint, choice


class Heart(Frame):
	def __init__(self, master):

		super().__init__(master)

		self.canvas = Canvas(master, bg = '#866F85')
		self.canvas.place(relx = 0, rely = 0, relwidth = 1, relheight=1)


		self.objects = []
		self.num = 0
		self.chars = ['love', 'love', 'te amo','love','te amo','karina ','karina','love','♪']
		self.char = '☆'

		self.create_obj()
		self.update()

	def create_obj(self):
		for i in range(200):
			obj = self.canvas.create_text(0,0, font= ('Arial',24))
			self.canvas.coords(obj, 500, 250)
			self.objects.append(obj)

	def draw(self, obj, x,y, color, char):  
		self.canvas.itemconfig(obj, fill = color, text=char)
		self.canvas.move(obj, x,y)
