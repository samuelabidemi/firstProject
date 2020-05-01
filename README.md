# firstProject
import tkinter as tk
from tkinter import ttk
import random
from datetime import datetime 
import tkinter.messagebox

font = {'font': ('arial',12,)}
class Library:

    def __init__(self, master):
        self.master = master
        self.master.title("Library System")
        self.master.geometry("1350x750+0+0")
        self.master.configure(background='grey')
       
        
        
        #The whole Frame begins from here

        MainFrame = tk.Frame(self.master) #sets the frame
        MainFrame.pack()
        #Project Name Frame
        top_frame_with_name = tk.Frame(MainFrame, width=1350, bd = 20, padx = 10, relief=tk.GROOVE)
        top_frame_with_name.pack(side=tk.TOP)
        self.libTitle = tk.Label(top_frame_with_name, width=40, **font,text="FUOYE LIBRARY MANAGEMENT SYSTEM")
        self.libTitle.grid()

       
        #Data Frame
        DataFrame = tk.Frame(MainFrame, width= 1350, height=70, bd = 20, padx = 20, pady=20, relief=tk.GROOVE )
        DataFrame.pack(side=tk.BOTTOM)


        #Tasks Frame(Exit, Reset etc.)
        OptionFrame = tk.Frame(MainFrame, width= 1350, height=70, bd = 20, padx = 20, pady=20, relief=tk.GROOVE )
        OptionFrame.pack(side=tk.BOTTOM)

        #User am#nd Book Details Frame
        user_details_frame = tk.Frame(MainFrame, width= 1350, height=400, bd = 20, padx = 20, pady=20, relief=tk.GROOVE )
        user_details_frame.pack(side=tk.BOTTOM)


        #For user info
        User_info_frame = tk.LabelFrame(user_details_frame, width = 700, height= 400, text = 'User Info', **font, bd = 10, relief= tk.GROOVE)
        User_info_frame.pack(side=tk.LEFT)

        Book_info_frame = tk.LabelFrame(user_details_frame, width = 500, height = 400, text='Book Details',**font, relief=tk.GROOVE )
        Book_info_frame.pack(side=tk.RIGHT)



        #Widgets
        #Title of Library User
        self.user_title = tk.Label(User_info_frame, **font, text="User Type:",  )
        self.user_title.grid(row=0,)
        self.user_title_entry =ttk.Combobox(User_info_frame, **font,   )
        self.user_title_entry['value']= ('', 'Mr', 'Mrs', 'Dr', 'Miss', 'Prof.')
        self.user_title_entry.current(0)
        self.user_title_entry.grid(row=0, column=1, sticky='W')

        #Type of User
        self.user_type = tk.Label(User_info_frame, **font, text="User Type:",  )
        self.user_type.grid(row=1,)
        self.user_type_entry =ttk.Combobox(User_info_frame, **font,  )
        self.user_type_entry['value']= ('', 'Student', 'Lecturer', 'Admin Staff', 'Non-academic Staff')
        self.user_type_entry.current(0)
        self.user_type_entry.grid(row=1, column=1, sticky='W')
        
        '''
        self.Lb = tk.Listbox(User_info_frame) 
        self.Lb.insert(1, 'Python') 
        self.Lb.insert(2, 'Java') 
        self.Lb.insert(3, 'C++') 
        self.Lb.insert(4, 'Any other') 
        self.Lb.grid(row=0) 
        '''
        

        #firstName of Library User
        self.user_firstName = tk.Label(User_info_frame, **font, text="Firstname:",  )
        self.user_firstName.grid(row=2)
        self.user_firstName_entry =tk.Entry(User_info_frame, )
        self.user_firstName_entry.grid(row=2, column=1) 

        #lastName of lib user
         #firstName of Library User
        self.user_lastName = tk.Label(User_info_frame, **font, text="Lastname:",  )
        self.user_lastName.grid(row=3)
        self.user_lastName_entry =tk.Entry(User_info_frame, )
        self.user_lastName_entry.grid(row=3, column=1) 


        #Matric/staff no
        self.user_MtrcOrStaNum = tk.Label(User_info_frame, **font, text="Matric/Staff No.:", padx=2, pady=2 )
        self.user_MtrcOrStaNum.grid(row=4)
        self.user_MtrcOrStaNum_entry =tk.Entry(User_info_frame, )
        self.user_MtrcOrStaNum_entry.grid(row=4, column=1) 

        #User_address
        self.user_address = tk.Label(User_info_frame, **font, text="Address:",  padx=2, pady=2 )
        self.user_address.grid(row=5)
        self.user_address_entry =tk.Entry(User_info_frame, )
        self.user_address_entry.grid(row=5, column=1) 

        #User contact number
        self.user_cntNum = tk.Label(User_info_frame, **font, text="Phone Number:",  padx=2, pady=2 )
        self.user_cntNum.grid(row=6)
        self.user_cntNum_entry =tk.Entry(User_info_frame, )
        self.user_cntNum_entry.grid(row=6, column=1) 

        #User's email
        self.user_mail = tk.Label(User_info_frame, **font, text="Email:",  padx=2, pady=2 )
        self.user_mail.grid(row=7)
        self.user_mail_entry =tk.Entry(User_info_frame, )
        self.user_mail_entry.grid(row=7, column=1) 

        #Book Title
        self.bk_title = tk.Label(User_info_frame, **font, text="Book Title:",  padx=2, pady=2 )
        self.bk_title.grid(row=0, column=3)
        self.bk_title_entry =tk.Entry(User_info_frame, )
        self.bk_title_entry.grid(row=0, column=4) 

        #Author
        self.bk_author = tk.Label(User_info_frame, **font, text="Author:",  padx=2, pady=2 )
        self.bk_author.grid(row=1, column=3, )
        self.bk_author_entry =tk.Entry(User_info_frame, )
        self.bk_author_entry.grid(row=1, column=4) 

        '''
        Name_of_user = tk.Entry(user_details_frame, **font, )
        Name_of_user.grid(row = 1, column = 0)
        matric_number = tk.Entry(user_details_frame, **font, )
        matric_number.grid(row = 2, column = 0)
        address = tk.Entry(user_details_frame, **font,bg = 'gray',  )
        address.grid(row = 3, column = 0)

        #staff or student department
        department = tk.Entry(user_details_frame, **font, )
        department.grid(row = 4, column = 0)
        '''


    

    #code to run the application
window = tk.Tk() 
app = Library(window)
window.title(" Library Management System")

window.resizable(False, False)
window.mainloop()
