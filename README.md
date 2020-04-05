# S4PCW
Sims 4 Python Script Workspace

Decompiler ใน Python 3 ด้วย unpyc3
สวัสดีผู้อ่านทุกท่านครับ บทความนี้จะพาผู้อ่านไปเรียนรู้การใช้งานเครื่องมือที่ชื่อว่า unpyc3 เพื่อ decompiler หรือถอดโค้ดจากไฟล์ .pyc ใน Python 3 กันครับ


โหลดไฟล์ unpyc3.py ได้จาก https://github.com/figment/unpyc3/raw/master/unpyc3.py

ในการเรียกใช้งานต้องวางไฟล์ unpyc3.py ไว้กับโฟลเดอร์ที่เก็บงานที่ต้องการ decompiler ครับ
ถอดโค้ด Python จากฟังก์ชั่นที่เรียกใช้งาน

สามารถถอดได้ตามตัวอย่างต่อไปนี้
>>> from unpyc3 import decompile
>>> def foo(x, y, z=3, *args):
... global g
... for i, j in zip(x, y):
... if z == i + j or args[i] == j:
... g = i, j
... return
...
>>> print(decompile(foo))
def foo(x, y, z=3, *args):
global g
for i, j in zip(x, y):
if z == i + j or args[i] == j:
g = i, j
return

ถอดโค้ด Python จากไฟล์ .pyc

หากต้องการถอดโค้ด Python จากไฟล์ .pyc
ให้วางไฟล์ unpyc3.py ไว้โฟลเดอร์เดียวกันกับไฟล์ .pyc ที่ต้องการ decompiler แล้วเปิดคอมมานด์ไลน์ ใช้คำสั่ง cd ไปยังโฟลเดอร์ที่เก็บไฟล์ที่ต้องการ decompiler

>>> a = 'ชื่อไฟล์.pyc'
>>> from unpyc3 import decompile
>>> print(decompile(a))

ตัวอย่าง
>>> a = 'hello.pyc'
>>> from unpyc3 import decompile
>>> print(decompile(a))
print('Hello')

ติดตามบทความต่อไปนะครับ
ขอบคุณครับ
