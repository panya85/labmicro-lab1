# labmicro-lab1

registers เป็นหน่วยความจำภายใน CPU ซึ่งในตัวโปรแกรม RISC-V มี registers ให้ทั้งหมด 32 ตัว แต่ละตัวก็จะมีหมายเลขกำกับของแต่ละตัว เริ่มจาก x0 ถึง x31 ซึ่ง registers แต่ละตัวจะมีหน้าที่แตกต่างกัน
โดยในที่นี้เราจะใช้ registers (x0,x1,x2,x3)
- x1 กำหนดให้เป็น Adress เริ่มต้น ที่ใช้ใส่ข้อมูลไวเพื่อให้ได้ output ออกมาเป็นตัวอักษรที่ต้องการ
- x2 ใช้ในการกำหนดให้ output ออกมาเป็นตัวอักษร แล้วแสดงผมที่ c0000000(data)
- x3 ใช้ใในการรับค่าที่เรากำหมดไว้ใน Adress 20-24 เพื่อให้ output ออกไปที่ Text l/O c0000000(data)
จากนั้น จะกลับมาเข้าลูปเพื่อจบโปรแกรมได้ด้วยเมื่อปริ้นถึง Adress 25 ซึ่งกำหนดไว้เป็น 00 ทำให้ค่า x3 มีค่าเท่ากับ 0 จึงถูกจั๊ม(กระโดด)ไป +16 ด้วยคำสั่ง beq x3,x0, +16 และติดลูปด้วยคำสั่ง jal x0,0 
