

## Git Workflow
- master สำหรับ deploy production (มีแค่ tag version เช่น v.1.0.0)
- develop สำหรับพัฒนาระบบอย่างเดียว
- feature แตกจาก develop branch เท่านั้น เพื่อพัฒนา feature ใหม่ๆ
- release แตกจาก develop เพื่อเตรียม deploy ระบบเวอร์ชั่นใหม่
- hot fix แตกมาจาก master เท่านั้น ในกรณีที่ production มีบัก
- bug แตกออกจาก release

#### อ้างอิง
- [link 1](https://medium.com/i-gear-geek/%E0%B8%A1%E0%B8%B2%E0%B8%97%E0%B8%B3%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%A3%E0%B8%B9%E0%B9%89%E0%B8%88%E0%B8%B1%E0%B8%81%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%81%E0%B8%B1%E0%B8%9A-git-workflows-%E0%B8%81%E0%B8%B1%E0%B8%99-e12609e9a8d2?fbclid=IwAR2klDGR6nZ1kvo44ArVWpPImxLMCamEHjcNwhEA_hv2JlQJQQnpUuzZHn0)
- [link 2](http://www.siamhtml.com/git-workflow-in-a-team/)
