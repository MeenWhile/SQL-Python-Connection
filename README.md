# SQL Python Connection

## Objective
โปรเจ็คนี้เป็นโปรเจ็คกลุ่มที่จัดทำร่วมกับสมาชิกอีก 2 คนเพื่อส่งในวิชา Basic Programming and Database Management ของสถาบันบัณฑิตพัฒนบริหารศาสตร์(NIDA) โดยวัตถุประสงค์ของโปรเจ็คนี้ คือการสร้างระบบจัดการข้อมูลสินค้าประเภทอุปกรณ์เสริมสวยของห้างสรรพสินค้าแห่งหนึ่งด้วย SQL และ Python

## 1. Create SQL Database
เริ่มต้น เราได้นำ data ซึ่งอยู่ในรูปแบบของ CSV เข้า MySQL เพื่อสร้าง SQL Database โดย data ชุดนี้มีลักษณะดัง ER Diagram ด้านล่าง

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/de6a7a1a-e6d7-4a7f-a636-745dbee8c56f)

## 2. Create product information management system by Python
ต่อมา เราได้สร้างระบบจัดการข้อมูลสินค้าขึ้นด้วย Python โดยได้แบ่งโปรแกรมออกเป็น 6 ส่วนนั่นคือ

1. Search
2. Advanced Search
3. Insert Data
4. Delete Data
5. Analytic
6. Insight

ซึ่งหน้าที่ที่ผมรับผิดชอบสำหรับโปรเจ็คนี้ คือส่วนของ 2. Advanced Search, 6.2 Meen Insight และการรวม code ของทุกคนให้สามารถรันด้วยกันได้ในไฟล์เดียว

### 1. Seach

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/c757e475-b9c3-47d4-84ea-adb15078caef)

เมื่อเริ่มรันโปรแกรม ตัวโปรแกรมก็จะถามว่าต้องการใช้งาน MENU ไหน โดยถ้าเราใส่เลข 1 เข้าไปในช่อง Input number โปรแกรมก็จะไปสู่ส่วนของการ Search

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/f85cf5f1-1c89-4497-a20d-384e8da27141)

จากนั้น โปรแกรมก็จะถามว่าต้องการ Search สินค้าด้วย product id หรือ model ซึ่งจากตัวอย่างนี้ เราได้ Search สินค้าด้วย product id : 81935

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/485bdfeb-67f6-4971-ac78-e2d329e6053a)

เมื่อกรอก product id เสร็จแล้ว โปรแกรมก็จะแสดงข้อมูลสินค้าของ product id นั้น พร้อมถามว่าต้องการที่จะ Search สินค้าอื่นต่อมั้ย ซึ่งถ้าเราใส่ N โปรแกรมก็จะย้อนกลับไปที่หน้า MENU เริ่มต้น

### 2. Advanced Search

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/5c153575-9e68-48b8-a0f3-e1ca1255f02f)

ต่อมาก็จะเป็นส่วนที่ 2 ของโปรแกรม(Advanced Search) โดยในส่วนของ Advanced Search นี้ เราต้องการให้โปรแกรมสามารถ Search ได้หลากหลายมากขึ้น และใกล้เคียงกับการแสดงผลด้วย SQL

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/0413b541-51c5-4192-8cfd-dac8053ac0d6)

โดยเมื่อเข้าสู่ส่วนของ Advanced Search แล้ว โปรแกรมก็จะถามว่าต้องการให้แสดงผล column ไหนบ้าง ซึ่งในตัวอย่างนี้ เราเลือกแสดงผล column C1, C4, C6, C10 หรือก็คือ column product_id, sub_id, current_price, likes_count
