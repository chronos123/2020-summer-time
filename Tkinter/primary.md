### tkinter documentation

https://m.runoob.com/python/python-gui-tkinter.html

### tkinter 创建窗口实例：
```py
root = tkinter.TK()

root.title

root.geometry('a x b')要用小写的x来确定大小
```



### 实例化以下内容，建立输入框，show为显示方式，通过place method来确定位置
```py
a = tk.StringVar()

b = tk.Entry(window, textvariable=a, show='*')
```


### 建立标签
```py
a = tk.Label 

tk.Label(window, text='用户名:').place(x=100, y=75)
```


### 建立新一级链接的子窗口
```py
a = tk.Toplevel(window)
```


### 建立按钮，command为一个函数调用
```py
a = tk.Button(window, text='登录', command=usr_log_in)
```


### 显示弹窗
```py
tk.messagebox.showinfo(title='welcome', message='欢迎您：' + usr_name)

tk.messagebox.showerror(message='密码错误')
```


### 将信息存入文件(以字典的数据类型)
```py
pickle.dump(a, file)
```


### 读取文件中信息
```py

try:

    with open('usr_info.pickle', 'rb') as usr_file:

    usrs_info = pickle.load(usr_file)


except FileNotFoundError:

    with open('usr_info.pickle', 'wb') as usr_file:

    usrs_info = {'admin': 'admin'}

    pickle.dump(usrs_info, usr_file)
```       
            
       
