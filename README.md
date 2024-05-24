# CodeMobile Challenge

1.  Create Angular Application

    - Theme ให้ใช้ Bootstrap จะใช้ ngx-bootstrap หรือ ng-bootstrap ก็ได้ตามที่ถนัด

2.  Routing 3 Pages

    - หน้า Login

      UI

      - input[type="email"] required
      - input[type="password"] required, minLength=8
      - submit button เข้าสู่ระบบ
      - implements ด้วย reactive form

      Condition

      - ถ้า form valid ตามเงื่อนไขให้ไปหน้า Home Page พร้อมทั้งเก็บ value ลง localstorage โดย key = token , value = new Date().getTime().toString()
      - ถ้า invalid ให้แสดง error message ตาม case ที่ error ใต้ input

    - หน้า Home Page

      UI

      - ให้ render ข้อมูลเป็น Table โดยที่ column มีดังนี้
        - Thumbnail
        - Title
        - Price
        - Stock
        - TotalPrice
        - ปุ่ม Detail
      - เพิ่ม dropdown menu
        - ทั้งหมด [แสดงสินค้าทั้งหมด]
        - ราคามากกว่า 1,000
        - เรียงเรตติ้ง [โดยให้สลับคำแสดงผลเมื่อกด ตัวอย่าง -> เรียงเรตติ้ง น้อยไปมาก, เรียงเรตติ้ง มากไปน้อย]
      - ปุ่มออกจากระบบ

      Condition

      - create service สำหรับเก็บ route ของ API เพื่อให้ง่ายต่อการ re-use
      - fetching data ด้วย httpClient ผ่าน URL [GET] https://dummyjson.com/products และ create interface เพื่อรอง mapper กับ response ของ API
      - Column TotalPrice ให้ใช้ Pipe ในการคำนวนการแสดงผลโดยที่ TotalPrice = stock \* price
      - เมื่อกดปุ่ม Detail ให้ไปหน้า DetailPage พร้อมส่ง id ผ่าน URL โดยใช้ RouterLink
      - กดปุ่ม dropdown ราคามากกว่า 1,000 ให้ใช้ Javascript filter สินค้าราคา > 1000 และมีส่วนลด > 0%
      - กดปุ่ม dropdown เรียงเรตติ้ง ให่้ ใช้ JavaScript ให้การ sort Rating desc/asc
      - กดปุ่มออกจากระบบให้ clear token ใน localStorage พร้้อมทั้ง redirect to Login Page

    - หน้า Detail Page

      UI

      - แต่่ง UI ตามสวยงามโดยให้เอาข้อมูล เหล่านี้มาแสดง
        - Images (carousel)
        - Title
        - Price
        - Stock
        - Description
        - TotalPrice

      Condition

      - fetching data ด้วย httpClient ผ่าน URL [GET] https://dummyjson.com/products/:id
      - TotalPrice ให้ใช้ Pipe ในการคำนวนการแสดงผลโดยที่ TotalPrice = stock \* price

3.  Private Routes & Lazy

- ให้ทำ LazyModule โดยที่ให้แบ่งเป็น 2 Module

  - Auth
    - Login Page
  - Core
    - HomePage
    - DetailPage

- ให้ทำ RouterGuard CanActivate
  - โดยให้ตรวจสอบว่า ถ้าไม่มี Key token ใน LocalStorage ให้ redirect ไปหน้า Login แต่ถ้ามี ให้ redirect ไปหน้า Home Page
