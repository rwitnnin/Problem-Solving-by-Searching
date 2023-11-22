# Problem-Solving-by-Searching
![pacman](https://github.com/rwitnnin/Problem-Solving-by-Searching/assets/150579607/d63e1dfa-0a5c-4a14-af64-867337291728)
![pacman1](https://github.com/rwitnnin/Problem-Solving-by-Searching/assets/150579607/667925b5-a201-4f10-9f09-5718a238654a)
bfsSearchStack ถูกสร้างเป็น queue โดยใช้คลาส util.Queue()
คู่ตัวเลขเริ่มต้น (problem.getStartState(), []) ถูกเพิ่มลงใน queue โดยเอา state และ actions ว่างเปล่าไปใส่
สถานะเริ่มต้นถูกเพิ่มเข้าไปใน visitedList เพื่อเก็บรายการของสถานะที่เคยเยี่ยมชม
ลูปทำงานไปเรื่อย ๆ จนกว่า queue จะว่าง
ในทุกการทำงานของลูป จะมีการนำ state-action ออกจากต้น queue
สำหรับทุกรายการที่เป็น successor ของ state ปัจจุบันที่ได้มาจาก problem.getSuccessors(state) โค้ดจะดึง state ถัดไป (n_state) และ action ที่เกี่ยวข้อง (n_direction)
ถ้า state ถัดไปยังไม่เคยเยี่ยมชม โค้ดจะดำเนินการต่อ
ถ้า state ถัดไปเป็นเป้าหมาย, ฟังก์ชันจะคืนลิสต์ของ actions ที่ทำไปจนถึงตอนนี้รวมกับ action ปัจจุบัน ซึ่งแทนเส้นทางที่เป็น soluton
ถ้า state ถัดไปไม่ใช่เป้าหมาย ก็จะนำ state และ actions ที่ได้มาเพิ่มลงใน queue เพื่อทำการสำรวจต่อ และ state ถัดไปจะถูกเพิ่มใน visitedList
สรุปแล้ว, โค้ดนี้ทำการค้นหาแบบ breadth-first เพื่อหาเส้นทางที่เป็น solution จากสถานะเริ่มต้นไปยังสถานะเป้าหมาย การค้นหาทำไปเรื่อย ๆ โดยการสำรวจ successor ของ state ปัจจุบัน และตรวจสอบเงื่อนไขสำหรับการเป็นเป้าหมาย และเพิ่ม state ลงใน queue ถ้าไม่ใช่เป้าหมาย
