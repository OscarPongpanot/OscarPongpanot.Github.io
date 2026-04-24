---
layout: default
---

# Lab 12.2.9 Applied Live Lab : Analyze Data 

**เป้าหมายของ Lab:** เพื่อฝึกฝนทักษะการทำความสะอาด ตรวจสอบ และวิเคราะห์ข้อมูลเบื้องต้น (Exploratory Analysis) ผ่านข้อมูลยอดขาย (Sales Order Details) ของ AdventureWorks2019 โดยใช้เครื่องมือใน Excel เช่น การหาค่ากลาง (Central Tendency), การสร้าง Pivot Table, การวิเคราะห์แนวโน้ม (Trend Analysis) และการใช้ Data Analysis Toolpak

---

## ส่วนที่ 1: การคำนวณค่ากลางและการประเมินข้อมูลเบื้องต้น (Calculate Central Tendencies)

ในส่วนนี้เราจะเปิดไฟล์ Excel `Sales Order Details` เพื่อทำความเข้าใจโครงสร้างของชุดข้อมูล (Data Profiling) และค้นหาข้อมูลเฉพาะเจาะจงผ่านการกรองข้อมูล (Filtering)

### ขั้นตอนที่ 1: หาจำนวนแถวทั้งหมดในชุดข้อมูล

**โจทย์:** 5. How many rows are in the full dataset in the All Sales Order Details tab?
(ตัวเลือก: 22045 / 60919 / 149053)

**วิธีตรวจสอบ:**
1. ไปที่ชีต `All Sales Order Details`
2. คลิกที่เซลล์ A1 จากนั้นกดคีย์ลัด `Ctrl + Shift + ลูกศรลง (Down Arrow)` เพื่อคลุมดำข้อมูลทั้งคอลัมน์
3. สังเกตที่แถบสถานะ (Status Bar) ด้านล่างขวาของหน้าจอ Excel จะแสดงค่า `Count:` ซึ่งบอกจำนวนบรรทัดทั้งหมด (อย่าลืมลบ 1 บรรทัดที่เป็น Header ออก)

![แสดงแถบ Status Bar ด้านล่างขวาของโปรแกรม Excel](<Comptia Assign Pic/12.2.9/1..png>)

**คำตอบ:** * `60919`

---

### ขั้นตอนที่ 2: วิเคราะห์ประเภทของข้อมูล

**โจทย์:** 6. What kind of information is in this dataset?

**วิธีตรวจสอบ:**
1. ดูที่แถวแรก (Header Row) ของตาราง เพื่อดูชื่อคอลัมน์ทั้งหมด
2. วิเคราะห์ว่าชื่อคอลัมน์ (เช่น SalesOrderID, ProductID, OrderQty, LineTotal ฯลฯ) สื่อถึงเรื่องอะไร ซึ่งจะเห็นได้ชัดเจนว่าเป็นรหัสคำสั่งซื้อ ข้อมูลสินค้า จำนวน และยอดขาย

**คำตอบ:** * `order IDs, product information, quantities, customer details and sales persons`

---

### ขั้นตอนที่ 3: ค้นหาราคาของสินค้าเฉพาะเจาะจง

**โจทย์:** 7. What is the unit price for the Water Bottle - 30oz.?
(ตัวเลือก: 0.99 / 2.99 / 12.50 / 1.37)

**วิธีตรวจสอบ:**
1. เปิดใช้งาน Filter โดยไปที่แท็บ `Data` > `Filter`
2. คลิกที่ปุ่ม Dropdown ที่คอลัมน์ชื่อ `Name` (หรือ ProductName)
3. พิมพ์ค้นหาคำว่า `Water Bottle - 30oz.` แล้วกด OK
4. ดูค่าในคอลัมน์ `UnitPrice` ของแถวที่ปรากฏขึ้นมา

![แสดงการใช้ Filter ค้นหาชื่อสินค้าและดูราคา](<Comptia Assign Pic/12.2.9/3..png>)

**คำตอบ:** * `2.99`

---

### ขั้นตอนที่ 4: ค้นหารหัสสินค้า

**โจทย์:** 8. What is the ProductNumber for Patch Kit/8 Patches

**วิธีตรวจสอบ:**
1. เคลียร์ Filter เดิมออก
2. คลิก Filter ที่คอลัมน์ `Name` พิมพ์ค้นหาคำว่า `Patch Kit/8 Patches`
3. ดูรหัสในคอลัมน์ `ProductNumber` ของแถวที่ปรากฏ
   
![แสดงการใช้ Filter ค้นหาชื่อสินค้าและดูราคา](<Comptia Assign Pic/12.2.9/4..png>)

**คำตอบ:** * `PK-7098`

---

### ขั้นตอนที่ 5: นับจำนวนคำที่ปรากฏในข้อมูล

**โจทย์:** 9. How many instances of Chain are in the Name column?
(ตัวเลือก: 250 / 86 / 19 / 583)

**วิธีตรวจสอบ:**
1. เคลียร์ Filter ออกทั้งหมด
2. คลิก Filter ที่คอลัมน์ `Name` เลือก `Text Filters` > `Contains...`
3. พิมพ์คำว่า `Chain` แล้วกด OK
4. คลุมดำข้อมูลที่ถูกกรอง แล้วดูจำนวน `Count` ที่แถบ Status Bar ด้านล่าง

![แสดงการใช้ Text Filter แบบ Contains](<Comptia Assign Pic/12.2.9/5..png>)

**คำตอบ:** * `250`

---

### ขั้นตอนที่ 6: ค้นหาชื่อพนักงานขายจากรหัสออร์เดอร์

**โจทย์:** 10. What is the Salesperson's FirstName associated with SalesOrderID 65157?

**วิธีตรวจสอบ:**
1. เคลียร์ Filter ออก
2. ไปที่คอลัมน์ `SalesOrderID` ใช้ Filter ค้นหารหัส `65157`
3. เลื่อนไปดูที่คอลัมน์ที่เก็บชื่อพนักงานขาย (FirstName)

**คำตอบ:** * `Linda`

---

## ส่วนที่ 2: การวิเคราะห์ข้อมูลด้วย Pivot Tables (Analyze Data with Pivot Tables)

ส่วนนี้เราจะใช้ Pivot Table เพื่อเจาะลึกดูประสิทธิภาพของสินค้าแต่ละตัว (Product Performance)

### ขั้นตอนที่ 1: วิเคราะห์ยอดรวมของสินค้า

**โจทย์:** 2. What is the total OrderQty for Product 712?

**วิธีตรวจสอบ:**
1. คลุมตารางข้อมูล ไปที่แท็บ `Insert` > `PivotTable` (สร้างใน Sheet ใหม่)
2. ลาก `ProductID` ไปไว้ที่ช่อง **Rows**
3. ลาก `OrderQty` ไปไว้ที่ช่อง **Values** (ให้แน่ใจว่าเป็น Sum of OrderQty)
4. เลื่อนหารหัสสินค้า `712` ใน Pivot Table แล้วดูผลรวมในช่อง OrderQty

![แสดงการจัดวาง Field ใน Pivot Table](<Comptia Assign Pic/12.2.9/6..png>)

**คำตอบ:** * `6121`

---

### ขั้นตอนที่ 2: ตีความหมายของข้อมูล

**โจทย์:** 3. According to the dataset pivot, Item 710 has a OrderQty sum of 90 - what does that mean?

**วิธีตรวจสอบ:**
1. วิเคราะห์จากโครงสร้างของ Pivot Table ที่เราเพิ่งสร้างขึ้น `OrderQty sum` หมายถึง ผลรวมของปริมาณสินค้าที่ลูกค้าสั่งซื้อไปทั้งหมด

**คำตอบ:** * `There are 90 of these items sold`

---

### ขั้นตอนที่ 3: Drill Down เจาะลึกข้อมูลสินค้า

**โจทย์:** 7. How many observations are in this sample? (จากการ Drill Down Product ID 712)

**วิธีตรวจสอบ:**
1. กลับไปที่ Pivot Table ดับเบิลคลิกที่ตัวเลขผลรวม (Value) ของ Product ID `712`
2. Excel จะสร้าง Sheet ใหม่ขึ้นมา (Drilldown) ที่มีเฉพาะข้อมูลของสินค้านี้
3. นับจำนวนแถวข้อมูลใน Sheet ใหม่นี้ (ไม่รวม Header)

**คำตอบ:** * `1192`

---

### ขั้นตอนที่ 4: คำนวณสถิติพื้นฐานของกลุ่มย่อย (Mean, Max, Min)

**โจทย์:** 8-10. What is the mean, highest, and lowest quantity ordered for AWC Logo Cap?

**วิธีตรวจสอบ:**
1. อยู่ใน Sheet ที่เกิดจากการ Drill Down ข้อมูล (Product 712)
2. หาค่าเฉลี่ย: พิมพ์สูตร `=AVERAGE(คลิกคลุมคอลัมน์ OrderQty)` (ปัดเป็นจำนวนเต็ม)
3. หาค่าสูงสุด: พิมพ์สูตร `=MAX(คลิกคลุมคอลัมน์ OrderQty)`
4. หาค่าต่ำสุด: พิมพ์สูตร `=MIN(คลิกคลุมคอลัมน์ OrderQty)`

![แสดงการพิมพ์สูตร Average, Max, Min](<Comptia Assign Pic/12.2.9/7..png>)

**คำตอบ:** * Mean: `5`
* Highest: `27`
* Lowest: `1`

---

### ขั้นตอนที่ 5: ค้นหาสินค้าขายดีที่สุด

**โจทย์:** 14. What is the product name that has been ordered the most based on the product id?

**วิธีตรวจสอบ:**
1. กลับมาที่ชีต Pivot Table หลัก
2. นำฟิลด์ `Name` (หรือ ProductName) ลงมาวางที่ช่อง **Rows** คู่กับ ProductID
3. คลิกขวาที่คอลัมน์ตัวเลขผลรวม OrderQty เลือก `Sort` > `Sort Largest to Smallest`
4. ดูชื่อสินค้าที่ขึ้นมาอยู่บรรทัดบนสุด

**คำตอบ:** * `AWC Logo Cap`

**โจทย์:** 15. What is the range of money spent for orders based on the LineItem?
(ตัวเลือก: $5.19 to $112.73 / $5.39 to $10.37 / $1.99 to $159.00)

**วิธีตรวจสอบ:**
1. กลับไปที่ Sheet `All Sales Order Details` (Sheet ข้อมูลหลัก)
2. โฟกัสที่คอลัมน์ `LineTotal` (ยอดขายรวมของแต่ละรายการ)
3. **วิธีที่ 1 (ใช้สูตร):** หาพื้นที่ว่างๆ แล้วพิมพ์สูตร `=MIN(คลิกคลุมคอลัมน์ LineTotal)` เพื่อหาค่าต่ำสุด และพิมพ์ `=MAX(คลิกคลุมคอลัมน์ LineTotal)` เพื่อหาค่าสูงสุด
4. **วิธีที่ 2 (ใช้ Filter):** คลิกเปิด Filter ที่คอลัมน์ `LineTotal` เลือก `Sort Smallest to Largest` (เรียงจากน้อยไปมาก) ตัวเลขบนสุดคือค่าต่ำสุด และตัวเลขล่างสุดของตารางคือค่าสูงสุด
5. นำค่าต่ำสุดและค่าสูงสุดที่ได้ มาประกอบกันเป็นช่วง (Range) เพื่อเทียบกับตัวเลือก

**คำตอบ:** * `$5.19 to $112.73`

---

## ส่วนที่ 3: การวิเคราะห์แนวโน้มและเปอร์เซ็นต์การเปลี่ยนแปลง (Trend Analysis and Percent of Change)

ในส่วนนี้เราจะดูข้อมูลความเปลี่ยนแปลงเมื่อเวลาผ่านไป (Time-Series Data) เปรียบเทียบปี 2012 และ 2013

### ขั้นตอนที่ 1: วิเคราะห์ช่วงเดือนที่ขายดีและขายน้อยที่สุด

**โจทย์:** 5. Which month has the highest quantities ordered over the full two year period? / 6. Which month in 2012 had the lowest quantity ordered? / 7.What is the sum of order quantity in August 2012?

**วิธีตรวจสอบ:**
1. กรองข้อมูลเอาเฉพาะปี 2012 และ 2013
2. สร้าง Pivot Chart โดยดึง `OrderDate` ใส่แกน X (จัดกลุ่มเป็น Year และ Month) และดึง `OrderQty` ใส่ช่อง Values
3. ดูจากกราฟแท่ง (หรือตาราง Pivot) ว่าเดือนไหนของทั้ง 2 ปีรวมกันสูงที่สุด (ตอบข้อ 5)
4. โฟกัสเฉพาะกราฟปี 2012 ดูว่าเดือนไหนที่แท่งกราฟต่ำที่สุด (ตอบข้อ 6)
5. โฟกัสเฉพาะกราฟปี 2012 ดูว่าเดือนสิงหาคมมีค่า Orderqty อยู่เท่าไหร่ (ตอบข้อ 7)

![แสดงกราฟ Pivot Chart ข้อมูลรายเดือน](<Comptia Assign Pic/12.2.9/8..png>)

**คำตอบ:** * 5. Highest month: `Jun`
* 6. Lowest month 2012: `Deb`
* 7. Sum of Orderqty Aug 2012: `154`
---

### ขั้นตอนที่ 2: คำนวณเปอร์เซ็นต์การเปลี่ยนแปลง (Percent of Change)

**โจทย์:** 7. Which month had the greatest percent change? / 8. Which months did not have an increase in the year 2013?

**วิธีตรวจสอบ:**
1. นำข้อมูลรวมยอด (Sum) ของแต่ละเดือนปี 2012 และ 2013 มาวางเรียงกันในตารางใหม่
2. สร้างคอลัมน์ใหม่เพื่อคำนวณ % Change โดยใช้สูตร: `=(ยอดปี 2013 - ยอดปี 2012) / ยอดปี 2012`
3. เปลี่ยน Format เซลล์ให้เป็น Percentage (%)
4. ดูว่าเดือนไหนมี % สูงที่สุด (ตอบข้อ 7) และเดือนไหนที่ค่าติดลบ หรือได้ค่า 0 (ตอบข้อ 8)

![แสดงหน้าต่างเปอร์เซ็นต์การเปลี่ยนแปลง Percent of Change](<Comptia Assign Pic/12.2.9/9..png>)

**คำตอบ:** * 7. Greatest % change: `Feb`
* 8. Months with no increase: `Jan , Dec`

---

## ส่วนที่ 4: การใช้ Excel Statistical Analysis Toolpak

ส่วนสุดท้าย เป็นการเรียกใช้ Add-in ทางสถิติของ Excel เพื่อลดเวลาในการพิมพ์สูตร

### ขั้นตอนที่ 1: รันคำสั่ง Descriptive Statistics

**โจทย์:** 2. What is the Median (rounded to the nearest dollar)? / 3. What is the Mode? (ใช้คอลัมน์ LineTotal)

**วิธีตรวจสอบ:**
1. ไปที่แท็บ `Data` จะเห็นปุ่ม `Data Analysis` ทางขวามือ (หากไม่มีต้องไปเปิด Add-ins ก่อน)
2. เลือก `Descriptive Statistics` แล้วกด OK
3. ช่อง Input Range ให้คลุมดำข้อมูลในคอลัมน์ `LineTotal`
4. ติ๊กถูกที่ช่อง `Summary statistics` แล้วกด OK ให้โปรแกรมประมวลผลออกเป็นหน้าต่างสถิติใหม่
5. ดูค่าตัวเลขในบรรทัดที่เขียนว่า **Median** และ **Mode** ![แสดงหน้าต่างผลลัพธ์ Descriptive Statistics](<Comptia Assign Pic/12.2.9/10..png>)

**คำตอบ:** * Median: `20.746`
* Mode: `10`

---
[🏠 กลับหน้าหลัก](https://oscarpongpanot.github.io)
