# Denoising Dirty Documents with AutoEncoder 📜➡📃

## 📁 Dataset

<p align="center">
    <img src="https://storage.googleapis.com/kaggle-media/competitions/kaggle/4406/media/23.png" alt= "Examples of Dirty Document">
</p>

ข้อมูลนี้เกี่ยวกับ**ภาพข้อความ** มาจาก [Denoising Dirty Documents](https://www.kaggle.com/c/denoising-dirty-documents/data) ใน kaggle ซึ่งประกอบไปด้วย 3 โฟลเดอร์ ดังนี้ 

1. train: ภาพข้อความที่มี noise จำนวน 144 ภาพ
2. train_cleaned: ภาพข้อความที่ไม่มี noise จำนวน 144 ภาพ ซึ่งภาพใน train และ train_cleaned จะเป็นภาพเดียวกัน (เพื่อใช้สอน model ว่าเราอยากได้ output เป็นแบบ train_cleaned นะ หรือก็คือ รูปที่ไม่มี noise ในเอกสาร)
3. test: ภาพข้อความที่มี noise ไว้ test จำนวน 72 ภาพ

## ⚙ AutoEncoder

AutoEncoder คือ Neural network รูปแบบหนึ่ง และเป็นการเรียนรู้แบบ Unsupervised learning โครงสร้างของ AutoEncoder ประกอบด้วย 

 - Encoder จะทำหน้าที่เข้ารหัสข้อมูล input แล้วจะได้ข้อมูลที่มีขนาด (มิติ) เล็กกว่า input เสมอ ซึ่งเรียกว่า Latent layer หรือ Code (มีหลายชื่อมาก)
 - Decoder จพทำหน้าที่ถอดรหัสข้อมูลจาก Latent layer หรือ Code ให้ได้ขนาด (มิติ) เท่ากับ input แต่แต่รายละเอียดภายในของรูปที่ได้จะไม่คมชัดเท่ากับรูป input 

<p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*q1ja8mfO7aMxbFQM5NF3Eg.png" alt= "autoencoder architecture">
</p>


## 📃 Result

เมื่อใช้ AutoEncoder กับ test โฟลเดอร์ แล้วจะได้ตัวอย่างผลลัพธ์ ดังนี้ ส่วนผลลัพธ์แบบทุกรูปสามารถดูได้ใน[ลิงก์นี้](https://github.com/mill-ornrakorn/Denoising-Dirty-Documents-with-AutoEncoders/tree/main/test_result)

<p align="center">
    <img src="https://github.com/mill-ornrakorn/Denoising-Dirty-Documents-with-AutoEncoders/blob/main/pic%20for%20readme/result_testset.png?raw=true" alt= "result_testset">
</p>

และลองใช้กับรูปอื่น ๆ ที่เป็นภาษาไทยดู 
<p align="center">
    <img src="https://github.com/mill-ornrakorn/Denoising-Dirty-Documents-with-AutoEncoders/blob/main/pic%20for%20readme/result_testset2.png?raw=true" alt= "result_testset2">
</p>


จะเห็นว่ารูปทั้งหมดถูกลบ noise ออกไปจนเกือบหมด และสามารถเห็นตัวข้อความได้ชัดเจน 


หมายเหตุ: รูป output ที่ได้จาก Autoencoder จะมีมิติเท่ากับ รูป input แต่รายละเอียดภายในของรูปที่ได้จะไม่คมชัดเท่ากับรูป input 
