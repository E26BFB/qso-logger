# QSO Logger

โปรแกรมบันทึก QSO (amateur radio contact log) แบบไฟล์เดียว ทำงานบนเบราว์เซอร์ ไม่ต้องติดตั้งและไม่ต้องใช้เซิร์ฟเวอร์

## คุณสมบัติ
- บันทึก QSO: callsign, วันที่/เวลา (UTC), ความถี่, โหมด, RST, ชื่อ, grid locator, QTH, หมายเหตุ
- ค้นหาได้ทุกช่อง
- ส่งออกเป็น **ADIF (.adi)** สำหรับโปรแกรม log อื่น และ **CSV**
- นำเข้าไฟล์ ADIF
- ข้อมูลเก็บในเบราว์เซอร์ (localStorage) บนอุปกรณ์นั้นเท่านั้น

## วิธีใช้
เปิดไฟล์ `index.html` ในเบราว์เซอร์ ไม่ต้องติดตั้งอะไรเพิ่ม

## Android APK
โฟลเดอร์ `android/` เป็นโปรเจกต์ WebView ที่ห่อ `index.html` ไว้ GitHub Actions (`.github/workflows/build-apk.yml`) จะ build APK ทุกครั้งที่ push ไป `main` ดาวน์โหลดได้จากแท็บ Actions > ผลการรัน > Artifacts (`qso-logger-debug-apk`)

หมายเหตุ: ไฟล์ `android/app/src/main/assets/index.html` เป็นสำเนาของ `index.html` ที่ราก ถ้าแก้ไฟล์ใดไฟล์หนึ่ง ต้องคัดลอกให้ตรงกัน

## หมายเหตุ
- เวลาในฟอร์มตั้งค่าเป็น UTC ตามมาตรฐาน amateur radio
- ข้อมูลไม่ได้ซิงก์ข้ามอุปกรณ์ ให้ใช้การส่งออก ADIF เพื่อย้ายข้อมูล
- ควรสำรองข้อมูลด้วยการส่งออก ADIF เป็นระยะ เพราะการล้างข้อมูลของเบราว์เซอร์จะลบข้อมูลด้วย

## License
MIT
