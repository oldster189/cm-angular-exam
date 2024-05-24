# CodeMobile Challenge

## สร้างโปรเจค React Typescript
<b>1. ติดตั้ง Library</b>
  - axios
  - react router dom
  - redux toolkit
  - react hook form
  - yup

<b>2. สร้าง Route ขึ้นมา 3 Page</b>
 - Login Page
 - Home Page
 - Detail Page
 - Summary Page

2.1 ค่าเริ่มต้น Redirect มาหน้า Login Page

<b>3. หน้า Login Page มี UI ดังนี้</b>

3.1 ช่อง input Email type="text"

3.2 ช่อง input Password type="password"

3.3 ปุ่มเข้าสู่ระบบ

3.4 Implement react-hook-form กับ Login Page

3.5 เพิ่ม Validation Yup ใน react-hook-form

- ตรวจสอบ Format Email โดยใช้ Regex
- ตรวจสอบความรหัสผ่าน ความยาว 8 ตัวขึ้นไป
  
3.5 เมื่อกดปุ่มเข้าสู่ระบบ ตรวจสอบ Email = aa@bb.cc และ Password = 12345678 

        - ถ้าถูกต้อง Redirect ไปหน้า Home Page
         
        - ถ้าผิดให้ Alert ข้อความ "Email or password incorrect"

<b>4. หน้า Home Page มีเงื่อนไขตามนี้</b>

4.1 fetch ข้อมูลโดยใช้ axios GET: https://dummyjson.com/products เขียนแบบ async await

4.2 แปลงข้อมูล JSON ข้อ 4.1 เป็น Interface (ชื่อ Product) 

4.3 แสดงข้อมูลที่ fetch ได้เป็น Table มี Column ดังนี้
  - Thumbnail
  - Title
  - Price
  - Stock
  - ปุ่ม Detail

4.4 เมือกดปุ่ม Detail ให้ส่ง id product ผ่าน url params ไปหน้า Detail Page
 
<b>5. เพิ่ม input ช่องค้นหาข้อมูลสินค้า ค้นหาชื่อสินค้าแบบ Debound Time(1 วินาที) และ contain string ในหน้า Home Page</b>

<b>6. เพิ่มปุ่ม Dropdown 5 เมนู ในหน้า Home Page</b>
  - ทั้งหมด (แสดงสินค้าทั้งหมด)
  - ราคามากว่า 1000 (กรองสินค้าที่มีราคา 1000 ขึ้นไป และมี %ส่วนลด มากกว่า 0) [ใช้ function Filter Javascript]
  - แสดงราคารวมต่อชิ้น (เพิ่ม Column ขึ้นมาอีก 1 Column สำหรับแสดง ราคารวมต่อชิ้น) [ใช้ function Map Javascript เพิ่ม key totalPrice เข้าไปใน interface Product เพื่อแสดงใน column]
  - เรียงเรตติ้ง (เรียง rating สินค้าแบบ desc และ price แบบ asc)  [ใช้  function Sort Javascript]
 
<b>7. หน้า Detail Page</b>

7.1 Get id product จาก params และ fetch ข้อมูลสินค้า GET:https://dummyjson.com/products/:id   

7.2 แสดงข้อมูลสินค้า ตามสวยงาม
  - Images 150*150
  - Title
  - Price
  - Stock
  
<b>8. ปริ้นข้อความใน Life Cycle ต่างๆ ของ ReactJS ในหน้า Detail Page </b>

<b>9. เพิ่ม Interceptor http axios นำมาใช้กับหน้า Home Page</b>

9.1 Add header key CMReq = “request” ตอน Request http

9.2 Add header key CMERes = “response” ตอน Response http


<b>10. กำหนดค่าเริ่มต้น Route path เมื่อพิมพ์ url path ผิด หรือไม่มีอยู่ใน route ที่กำหนด ให้ทำเงื่อนไขตามนี้</b>

10.1 ถ้า ยังไม่ได้ Login ให้ Redirect มาหน้า Login Page

10.2 ถ้า Login แล้วให้ Redirect มาหน้า Home Page


<b>11. ติดตั้ง material ui theme https://mui.com/</b>

11.1 เปลี่ยน UI หน้า Login Page เป็น material ui ตามความสวยงาม


<b>12. ติดตั้ง Tailwindcss </b>

12.1 ปรับปรุง UI หน้า Home Page โดยใช้ tailwind css ตามความสวยงาม


<b>13. ติดตั้ง Redux Toolkit </b>

13.1 สร้าง productSlice สำหรับเก็บข้อมูล product หน้า Home Page และเพิ่ม Logic ในหน้า Home Page บันทึกข้อมูลเข้า store


<b>14. สร้าง Summary Page </b>

14.1 แสดงราคารวมทั้งหมด (คำนวนราคาสินค้าทั้งหมด ของ array สินค้า ให้ดึงมาจาก productSlice) [ใช้ function reduce Javascript]


<b>15. แสดงตัวอย่างการใช้ useMemo และ useCallback ในหน้า Home Page</b>
 
