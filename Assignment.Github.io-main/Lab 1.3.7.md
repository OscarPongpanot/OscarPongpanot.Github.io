# Lab 1.3.7: Database Design in Microsoft Access

**เป้าหมายของ Lab:** เพื่อทำความเข้าใจเกี่ยวกับตาราง (Tables) และความสัมพันธ์ (Relationships) ในฐานข้อมูล Microsoft Access โดยจำลองสถานการณ์การใช้งานฐานข้อมูลเพื่อติดตามข้อมูลการขาย (Sales data)

---

## ส่วนที่ 1: การสำรวจโครงสร้างและตอบคำถามเบื้องต้น

ในส่วนนี้เราจะเปิดตารางต่างๆ ในฐานข้อมูลเพื่อตรวจสอบฟิลด์และความสัมพันธ์ เพื่อหาคำตอบให้กับคำถามทั้ง 3 ข้อ

### ขั้นตอนที่ 1: ตรวจสอบ Data Type ในตาราง Employees

**โจทย์:** The locations field on the Employees table is set to the ______________ data type.

**วิธีตรวจสอบ:**
1. ที่หน้าต่าง Navigation Pane ด้านซ้ายมือ ภายใต้หัวข้อ **Tables**
2. คลิกขวาที่ตาราง `Employees`
3. เลือก **Design View**
4. ในหน้าต่าง Design View ให้ค้นหา Field Name ที่ชื่อว่า `locations` แล้วดูค่าในคอลัมน์ **Data Type**

![แสดงหน้าต่าง Design View](<Comptia Assign Pic/1.3.7/1..png>)

**คำตอบ:** * `Short text`

---

### ขั้นตอนที่ 2: ตรวจสอบความสัมพันธ์ของตาราง Orders

**โจทย์:** Which of the following tables are related to the Orders table?

**วิธีตรวจสอบ:**
1. ไปที่เมนู Ribbon ด้านบน เลือกแท็บ **Database Tools**
2. คลิกที่ไอคอน **Relationships**
3. หน้าต่างความสัมพันธ์จะแสดงขึ้นมา ให้สังเกตที่ตาราง `Orders` ว่ามีเส้นความสัมพันธ์ (Relationship lines) โยงไปหาตารางชื่ออะไรบ้าง

![แสดงหน้าต่าง Relationships ที่เห็นตาราง Orders](<Comptia Assign Pic/1.3.7/2..png>)

**คำตอบ:** * `Customers, Employees, products`

---

### ขั้นตอนที่ 3: ค้นหา Foreign Key ในตาราง Products

**โจทย์:** ______________ is a foreign key field in the Products table.

**วิธีตรวจสอบ:**
1. กลับมาที่ Navigation Pane ด้านซ้ายมือ 
2. คลิกขวาที่ตาราง `Products` แล้วเลือก **Design View** (หรือดูประกอบจากหน้าต่าง Relationships ในขั้นตอนที่ 2)
3. ค้นหาฟิลด์ที่ทำหน้าที่เป็น Foreign Key (คีย์นอก) ซึ่งมักจะเป็นฟิลด์ที่ใช้เชื่อมโยงกับ Primary Key (คีย์หลัก) ของตารางอื่น เพื่อระบุหมวดหมู่หรือประเภท

![แสดงหน้าต่าง Design View ของตาราง Products หรือเส้นความสัมพันธ์](<Comptia Assign Pic/1.3.7/2..png>)

**คำตอบ:** * `ProductType`
