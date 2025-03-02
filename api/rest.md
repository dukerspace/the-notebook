---
id: restful
title: RESTful
type: docs
path: the-notebook/api/rest
---

### RESTful
1. การตั่งชื่อต้องใช้ nouns อย่าใช้ verbs
2. อย่าใช้ GET ในการแก้ไขข้อมูลใดๆ ทั่งสิ้น หรือสร้างข้อมูลใหม่
3. ให้ใช้คำ nouns แบบพหูพจน์ (plural nouns) (ใช้ /authors แทน /author)
4. ใช้ Standard HTTP Method (GET: ดึงข้อมูล, POST: สร้างข้อมูล, PUT: อัพเดตข้อมูล, DELETE: ลบข้อมูล)
5. เปิดใช้งาน overriding HTTP method
```
$.ajax({
  url: "http://localhost/api/book/2",
  type: "POST",
  data: JSON.stringify(data),
  headers: {
      "Content-Type": "application/json",
      "X-HTTP-Method-Override": "PUT" },
})
```
6. ใช้ sub name ในการเชื่อมความสัมพันธ์ของของมูล (GET /books/2/author/10 ดึงข้อมูลผู้แต่งหมายแลข 10 ที่หนังสือหมายเลข 2)
7. ควรระบุ content-type ของการสื่อสารด้วยทั่ง clienกt และ server
8. อย่าลืมระบุ version API ด้วย
9. ใช้ HTTP Status Codes คู่ไปกับการใช้ Message ในการจัดการกับ Error ขอระบบ
```
- 200 OK – [GET]
- 201 CREATED – [POST/PUT/PATCH]
- 204 NO CONTENT – [DELETE]
- 304 NOT MODIFIED
- 400 INVALID REQUEST – [POST/PUT/PATCH]
- 401 UNAUTHORIZED
- 403 FORBIDDEN
- 404 NOT FOUND
- 500 INTERNAL SERVER ERROR
```
10. ในการดึงข้อมูลที่ซับซ้อน หรือมี state เยอะๆ ให้ทำ Query String  ด้วย GET (GET /api/v1/books?fields=name,price,author,type,categories&sort=asc&page=1&limit=10)

#### credit
- [algorithmtut](https://www.algorithmtut.com/%E0%B9%80%E0%B8%A5%E0%B8%B4%E0%B8%81%E0%B9%80%E0%B8%82%E0%B8%B5%E0%B8%A2%E0%B8%99-restful-api-%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B9%81%E0%B8%A2%E0%B9%88%E0%B9%86/)

----
1. HTTP GET 
This retrieves a resource from the server. It is idempotent. Multiple identical requests return the same result. 
 
2. HTTP PUT 
This updates or Creates a resource. It is idempotent. Multiple identical requests will update the same resource. 
 
3. HTTP POST 
This is used to create new resources. It is not idempotent, making two identical POST will duplicate the resource creation. 
 
4. HTTP DELETE 
This is used to delete a resource. It is idempotent. Multiple identical requests will delete the same resource. 
 
5. HTTP PATCH 
The PATCH method applies partial modifications to a resource. 
 
6. HTTP HEAD 
The HEAD method asks for a response identical to a GET request but without the response body. 
 
7. HTTP CONNECT 
The CONNECT method establishes a tunnel to the server identified by the target resource. 
 
8. HTTP OPTIONS 
This describes the communication options for the target resource. 
 
9. HTTP TRACE 
This performs a message loop-back test along the path to the target resource. 
