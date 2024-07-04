# ========= SENTRY.IO =================

# ********* ข้อดี *****************
# -ติดตั้งง่าย
# -มี GUI สวยงามใน Dashboard ให้ใช้ 
# -ฟรี
# - มีการระบุ OS , ip device ของ user ที่ใช้ตลอด

# ********* ข้อเสีย *************** 
# -ปรับแต่งค่อนข้างยาก  
# -ไม่ได้ระบุปัญหาชัดขนาดนั้น ลูกเล่นไม่ได้แพรวพราว 
# -การ trace ยังไม่ได้ระบุ issue ได้ชัดเจนทางผู้พัฒนายังต้องไล่ค้นหาcodeที่มีปัญหาเองอยู่

# ==============================================================================================

# *********** การติดตั้งใน C# project ********** 

# 1.)โดยเราจะทำการผูกบัญชี Github กับตัว Sentry.io ในplatform ให้เรียบร้อยก่อนเริ่มลงมือ
# เข้าไปที่ platform จากนั้น Setup ข้อมูลทั่วไปให้เรียบร้อยก่อนเช่น ชื่อทีม ชื่อ user


# 2.)ไปที่แถบเมนูหลัก Clickเข้าไปที่เมนู Projects จากนั้นสังเกตมุมขวาบนมีคำว่า Create Project ให้กดเข้าไป

![messageImage_1720096837339](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/4fd00531-c557-43a2-b98c-95ba89210d59)



# 3.)กดเลือก Framework หรือภาษาที่เราใช้กับโปรเจ็คให้เรียบร้อย จากนั้นตั้งชื่อ Project ของเรา
![messageImage_1720097674500](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/964a61c0-a3d7-4688-a64a-a1c896bc1f19)


# 4.)ทีนี้เมื่อเราสร้างเสร็จจะมี Example คอยบอกขั้นตอนการติดตั้ง package คร่าวๆ โดยเราทำการติดตั้ง package 2 ตัวนี้ใน Nuget ให้เรียบร้อยก่อน
# มีสองตัว ค้นหาเอาใน Nuget
# > Sentry.AspNetCore
# > Sentry.Profiling
![messageImage_1720096723825](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/e05384a6-cf40-4023-9bf8-3d87cb0e8ce0)



# 5.)ทำการเชื่อมต่อระหว่างโปรเจ็คเรากับตัวSentry.io โดยเข้ามาในโปรเจ็คเราใน Vscode
# ไปที่ appsettings.json จากนั้นเขียนcodeลงไปตามนี้
![messageImage_1720096702242](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/011c85c3-47e8-4fb2-9d52-598836bf02e5)



# 6.)เข้าไปที่การตั้งค่าของตัวโปรเจ็คใน Dashboard หรือ Projects > ตัวโปรเจ็คที่เราสรา้ง > settings
![messageImage_1720096804790](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/e3423590-7718-4bea-bbb6-860e3bd32092)



# 7.)หาคำว่า Client Keys จากนั้นเข้าไป Copy ตัว DNS ที่เข้าให้มา
![messageImage_1720097647367](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/3cc1b7bf-81c8-4259-826e-67a3a8632ca0)


# 8.)กลับมาใน project ของเราใน VScode ให้เข้าไปที่ไฟล์ appsettings.json
# ไปทำการเพิ่ม DNS ลงใน appsettings.json
![messageImage_1720097856972](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/6d4a32c0-e2cc-4f69-9c21-00399b5c9929)


# 9.)ไปที่ Vs code > Programe.cs  จากนั้นเพิ่มคำสั่งนี้เข้าไปในโค้ด >> builder.WebHost.UseSentry();

# 10.)ทำการติดตั้ง SDK ในส่วนโปรเจ็คของเรา โดยเข้าไปที่ Programe.cs
# ทำการ copy โค้ดชุดนี้ในExample ไปวางไว้ใน Program.cs และใส่ DNS ให้เรียบร้อย
![messageImage_1720096746745](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/dbdc1c61-3c11-4890-a0fb-37252a227d9f)



# 11.)ทีนี้ลอง dotnet watch run ตัวโปรเจ็คของเราแล้วทำ Transaction สักอย่างนึงเพื่อไปเช็ค Eventในตัว Sentry.io > ISSUE
# - โดยในส่วนนี้ของSentry จะแสดงแค่เวลาเกิดปัญหาขึ้นในตัวโปรแกรมของเรา เพื่อนๆลองทำอะไรสักอย่างให้มัน Error ดูสิ
![messageImage_1720097942632](https://github.com/belliorgabxl/Sentry_Document/assets/126590171/392b8494-0fd3-4edb-baec-0cbcabe40e0f)










