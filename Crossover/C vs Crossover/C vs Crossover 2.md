ตอนนี้ผมจะเล่าขั้นตอนการออกแบบ crossover ที่ใช้ทดลอง


1. ขั้นตอนแรกในการออกแบบ crossover จะต้องเริ่มจากกัดวัดเสียก่อน
( บางท่านอาจจะตบเข่าแล้วกล่าวว่า กุว่าแล้วววว~ )

คุณอาจจะสามารถเอากราฟจาก datasheet ที่โรงงานให้มา มาใช้ในการออกแบบ crossover ก็ได้
แต่ถ้าจะให้แม่นยำที่สุดก็ต้องวัดจริงหลังจากใส่ลำโพงลงตู้เรียบร้อยแล้ว (ซึ่งอันนี้สำคัญมาก จะวัดลำโพงโดยยังไม่ใส่ตู้ก็จะไม่ได้ผลดีที่สุด)

อันนี้เป็นเหตุผลที่ผมใช้ bi-wire เพราะจะทำให้ต่อ woofer และ tweeter แยกจากกันได้ง่ายขึ้น บางท่านสามารถเดินสายออกมาทาง port ได้เช่นกัน แต่ในกรณีของผมการเดินสายไฟผ่าน port นั้นทำได้ยากเพราะ port ค่อนข้างยาวและขดอยู่สองชั้น

ขั้นตอนการวัดผมทำตามบทความ
https://docs.google.com/document/d/1K_Ayk_l8lwntYFocBcB9dnN_VmSE6B11esgMWWMnqXw
ซึ่งหวังว่าทุกคนจะคุ้นเคยกันดี : D

เอาเป็นว่าผมไม่ลงวิธีวัดละเอียดนะ ใครสงใสตรงไหนก็คอมเม็นถามได้เลย

![[Crossover/C vs Crossover/pic/02_01.png]]

2. วัดลำโพงผมใช้แรงดันไฟไม่มาก

![[Crossover/C vs Crossover/pic/02_02.png]]

3. จัดห้องเล็กน้อยและวางลำโพงห่าง 50 ซม.

![[Crossover/C vs Crossover/pic/02_03.png]]

4. Impulse 

Impulse Response วันนี้จัดว่าดูดีเลย
first reflection เข้ามาหลัง 5 ms

![[Crossover/C vs Crossover/pic/02_04.png]]

5. วัด woofer far field

![[Crossover/C vs Crossover/pic/02_05.png]]

6. วัด tweeter far field

(รูปลำโพงผมไม่ได้ถ่ายตอนย้ายสายมา ให้คิดว่าสายลำโพงเสียบอยู่ที่ binding post คู่บน)
![[Crossover/C vs Crossover/pic/02_06.png]]

7. วัด woofer และ tweeter พร้อมกัน
(รูปไม่ได้ถ่ายเช่นกัน อันนี้จะมีสายอีกคู่หนึ่งเชื่อมระหว่าง binding post ชุดบนและล่าง)

![[Crossover/C vs Crossover/pic/02_07.png]]

8. วัด woofer และ port แบบ near field
![[Crossover/C vs Crossover/pic/02_08.png]]

9. รวมค่า Frequency Response (FR) ของ woofer

วิธีการโดยสังเขป
0. ปรับเสียง port ตามสมการ 20 x log(Dp/Ds) โดย Dp คือเส้นผ่านศูนย์กลางของ port และ Ds คือเส้นผ่านศูนย์กลางลำโพง หรือ 10 x log(Ap/Sd) Ap พื้นที่หน้าตัดของปาก port และ Sd คือพื้นที่หน้าลำโพงจาก T/S parameter 
1. เอาเสียงจาก port และ woofer มารวมกัน
2. แก้ diffraction ด้วยโปรแกรมคำนวณอื่นๆ
3. ทำ alignment ผลลัพธ์หลังแก้กับ woofer far field
4. ต่อ FR ทั้งสองเข้าด้วยกัน

ก็จะได้ FR ของ woofer
![[Crossover/C vs Crossover/pic/02_09.png]]

10. โยนค่าต่างๆ ลงโปรแกรมออกแบบ crossover

ซึ่งผมใช้โปรแกรม VituixCAD 2 
ผมก็ใส่ค่าทั้ง FR และ Impedance ของลำโพงลงไป
และต่อลำโพงกับสัญญาณแบบเปล่า ๆ ก่อน

![[Crossover/C vs Crossover/pic/02_10.png]]

11. ปรับ delay ของ tweeter

ผมก็จะ overlay FR ที่ได้จากการเปิด woofer และ tweeter พร้อมกัน ลงบน Power & DI
จากนั้นก็ปรับเวลาในวงกรมสีฟ้า ให้กราฟทั้งสองเส้นใกล้เคียงกันที่สุด

![[Crossover/C vs Crossover/pic/02_11.png]]


12. ออกแบบ crossover

วิธีการออกแบบนั้น คุณอาจจะต้องศึกษาวงจร crossover แบบต่าง ๆ มาก่อน
จากนั้นก็ลอง "มั่ว" ปรับนู้น ปรับนี้ดู จนผลออกมาดีที่สุด

วงจรที่ควรศึกษาได้แก่

1. First order high/low/band-pass filter
2. Second order high/low/band-pass filter
3. Third order high/low/band-pass filter
4. L-pad
5. Serial/Parallel notch filter 

ซึ่งผมอาจจะเอามาเล่าวันหลัง แต่น่าจะนานซักหน่อย
ระหว่างนี้โปรแกรมจะมี LIB ตัวอย่าง ซึ่งสามารถใช้ศึกษาได้เช่นกัน

![[Crossover/C vs Crossover/pic/02_12.png]]

13. สิ่งสำคัญอย่างนึงของวงจร crossover 
คือ phase ของ woofer และ tweeter ที่ตำแหน่งจัดตัด crossover จะต้องเท่ากัน

วิธีเช็คง่าย ๆ วิธีนึงคือ invert ลำโพงดอกนึง ถ้าเสียงมันหักลงไปเยอะ ๆ นั้นคือใช้ได้เลย

![[Crossover/C vs Crossover/pic/02_13.png]]

14. วงจร C ที่ tweeter ตัวเดียว
แต่เนื่องจาก tweeter มันดังกว่า woofer มากผมขอใส่ R เพิ่มอีกตัวหนึ่ง
ส่วนผลจะออกมาเป็นอย่างไร เสียงจะดีไหม โปรติดตามตอนต่อไป

![[Crossover/C vs Crossover/pic/02_14.png]]

