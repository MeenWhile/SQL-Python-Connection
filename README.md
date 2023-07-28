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

เมื่อกรอก product id เสร็จแล้ว โปรแกรมก็จะแสดงข้อมูลสินค้าของ product id นั้น พร้อมถามว่าต้องการที่จะ Search สินค้าอื่นต่อหรือไม่ ซึ่งถ้าเราใส่ N โปรแกรมก็จะย้อนกลับไปที่หน้า MENU เริ่มต้น

### 2. Advanced Search

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/5c153575-9e68-48b8-a0f3-e1ca1255f02f)

ต่อมาก็จะเป็นส่วนที่ 2 ของโปรแกรม(Advanced Search) โดยในส่วนของ Advanced Search นี้ เราต้องการให้โปรแกรมสามารถ Search ได้หลากหลายมากขึ้น และใกล้เคียงกับการแสดงผลด้วย SQL

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/0413b541-51c5-4192-8cfd-dac8053ac0d6)

โดยเมื่อเข้าสู่ส่วนของ Advanced Search แล้ว โปรแกรมก็จะถามว่าต้องการให้แสดงผล column ไหนบ้าง ซึ่งในตัวอย่างนี้ เราเลือกแสดงผล column C1, C4, C6, C10 หรือก็คือ column product_id, sub_id, current_price, likes_count

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/1213678a-deea-4f98-a0eb-ced73b600e54)

จากนั้น โปรแกรมก็จะถามต้องการแสดงผลกี่ row โดยในตัวอย่างนี้ เราต้องการแสดงผลทุก row จึงใส่ * ลงไป

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/8f431f30-a2a4-485f-b1c9-f14250e97cc5)

เมื่อใส่จำนวน row เสร็จแล้ว เราสามารถปรับแต่งการ search ได้อีกเล็กน้อย เช่น

1. W = ใช้ WHERE เพื่อ filter data
2. G = ใช้ GROUP BY เพื่อ group data ที่เหมือนกัน
3. O = ใช้ ORDER BY เพื่อ sort ลำดับของ data
4. E = ใช้ Export data ที่ได้ ออกมาเป็นไฟล์ CSV
5. N = จบการปรับแต่ง

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/b4b0460c-0e4f-4ecd-b426-5da0eaba7e39)
![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/b393ec16-9354-49bc-8d2a-e828d91dc0c3)

โดยเมื่อปรับแต่งเสร็จแล้ว โปรแกรมก็จะแสดงผล dataFrame ออกมา และก็จะ export dataFrame ออกมาเป็น CSV ถ้าเราเลือก E = Export data ในส่วนของการปรับแต่ง จากนั้นโปรแกรมก็จะถามต่อว่าต้องการสร้าง dataFrame ต่อหรือไม่ ซึ่งถ้าเราไม่ต้องการสร้างต่อ ก็สามารถใส่ N เพื่อย้อนกลับไปยังหน้า MENU

### 3. Insert Data

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/4b66b6ba-e7cd-4062-91d4-0aaebb5476e1)

ต่อมาก็จะเป็นส่วนที่ 3 Insert Data ซึ่งในส่วนนี้ เราสามารถให้ user add data เพิ่มเข้าไปใน dataFrame ได้ โดย user จะต้องใส่ข้อมูลต่าง ๆ สำหรับ data ตัวใหม่นี้

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/b713144f-a851-4898-926a-8dfa61c62e0d)
![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/237db2fa-4a06-4558-a8cc-172fb54fc996)

### 4. Delete Data

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/5691586d-8941-4f41-ba50-b13baebaea69)

ต่อไปจะเป็นในส่วนที่ 4 Delete Data โดยในส่วนนี้ เราสามารถลบ data ออกจาก dataFrame ได้ โดยการใส่ product_id ของ data ที่ต้องการจะลบ

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/904eab5c-139c-4afe-bee3-fac779500e04)

ซึ่งเมื่อใส่ product_id ของ data ที่ต้องการจะลบแล้ว โปรแกรมก็จะแสดงข้อมูลของ data ที่ต้องการลบเพื่อให้ user สามารถตรวจสอบได้ว่า data ที่จะลบนั้น ถูกต้องหรือไม่ โดยถ้าถูกต้องแล้ว user สามารถใส่ Y เพื่อยืนยันการ delete data

![image](https://github.com/MeenWhile/SQL-Python-Connection/assets/125643589/afc627e6-1305-4d00-8055-e6a63b15f6d8)
