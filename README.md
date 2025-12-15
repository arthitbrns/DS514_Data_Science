<div align="center"><b>Credit Card Approval Analysis and Predictive Modeling</b></div>

<div align="center">(การวิเคราะห์และการสร้างแบบจำลองคาดการณ์การอนุมัติบัตรเครดิต)</div>

1. Introduction

	สถาบันการเงินอนุมัติ/ปฏิเสธการสมัครบัตรเครดิต โดยพิจารณาจากข้อมูลผู้สมัคร โดยกระบวนการพิจารณาอาจใช้เวลานานและขึ้นอยู่กับดุลยพินิจของนักวิเคราะห์สินเชื่อ ซึ่งอาจนำไปสู่ความเสี่ยงหรือการสูญเสียโอกาสทางธุรกิจการสร้างแบบจำลองเพื่อทำนายผลการอนุมัติบัตรเครดิตโดยอัตโนมัติ ทำให้เพิ่มความรวดเร็วและความแม่นยำในการตัดสินใจ และสามารถรลดความเสี่ยงทางการเงิน (อัตราการผิดนัดชำระหนี้ - Default Rate) รวมถึงเพิ่มประสิทธิภาพในการดำเนินงาน (Operational Efficiency) ของฝ่ายอนุมัติสินเชื่อของธนาคารและสถาบันการเงิน (ฝ่ายบริหารความเสี่ยง, ฝ่ายการตลาด, ฝ่ายปฏิบัติการ) 

2. Problem Statement/Background

	การทำนายผลการอนุมัติบัตรเครดิต (Approved หรือ Rejected) จากข้อมูลของผู้สมัครที่ให้มาด้วยความแม่นยำสูง และสามารถตัดสินใจได้อย่างอัตโนมัติ จะสามารถลดความเสี่ยงทางการเงิน (อัตราการผิดนัดชำระหนี้ - Default Rate) และทำให้กระบวนการการวิเคราะห์และการอนุมัติสินเชื่อมีประสิทธิภาพมากขึ้น โดยแนวทางการวิเคราะห์จะดำเนินตาม Data Analysis & Data Science Framework ต่อไปนี้

 <div align="center">
<img width="825" height="424" alt="image" src="https://github.com/user-attachments/assets/12eae9ce-608e-4bfd-9a41-172e04db9f07" />

ภาพที่ 1 Data Analytic Framework</div>

<div align="center">
<img width="900" height="437" alt="image" src="https://github.com/user-attachments/assets/58b1a636-0c56-47c5-909a-bc34d754e159" />

ภาพที่ 2 Data Science Framework</div>

3. Data Analytics Methodology

3.1 Analytical Questions 
เพื่อค้นหาคุณลักษณะของผู้สมัคร (เช่น อายุ, รายได้, ประเภทงาน) ที่มีความสัมพันธ์กับการอนุมัติมากที่สุด และหากลุ่มลูกค้า (Segments) ที่มีความเสี่ยงสูง/ต่ำ ที่แตกต่างกันชัดเจน

3.2. Data Sources/Attributes
 	Kaggle Dataset: "Credit Card Approvals (Clean Data)" (ซึ่งจำลองมาจากข้อมูลการสมัครบัตรเครดิต) 
ข้อมูลในทางปฏิบัติ: ฐานข้อมูลภายในของธนาคาร/สถาบันการเงิน (ข้อมูลการสมัคร, ประวัติสินเชื่อ, ข้อมูลเครดิตบูโร)

<div align="center">
<img width="1050" height="297" alt="image" src="https://github.com/user-attachments/assets/bebdb793-1d9d-41fb-af58-016d2cc9d503" />

ภาพที่ 3 ตัวอย่าง Data Set </div>

<div align="center">
<img width="1050" height="413" alt="image" src="https://github.com/user-attachments/assets/122cd5d4-8fcd-47dc-9a2f-0c9053572329" />

ภาพที่ 4 ตัวอย่าง Data Dictionary</div>

3.3 Data cleaning and preprocessing 
เนื่องจากเป็น "Clean Data" จะเน้นการตรวจสอบขั้นสุดท้าย การจัดการกับค่าที่หายไป (Missing Values) ที่ยังอาจมีอยู่


4. Analytics Methodology 

4.1 EDA techniques: การวิเคราะห์ความถี่และค่าสถิติเชิงพรรณนา เพื่อดูความสัมพันธ์ของแต่ละคุณลักษณะกับผลการอนุมัติ

<div align="center">
<img width="1050" height="218" alt="image" src="https://github.com/user-attachments/assets/3272ef6f-c6db-4fbb-a022-99deb583eb24" />
 
ภาพที่ 5 สถิติเชิงพรรณนา (Descriptive Statistics)</div>

 <div align="center">
 <img width="940" height="377" alt="image" src="https://github.com/user-attachments/assets/c6276400-0358-4eca-a15b-fb0fe94a4f93" />

ภาพที่ 6 Pivot Table and Graph</div>

4.2 Visualization strategy: Heatmap สำหรับ Correlation Matrix

<div align="center">
 <img width="940" height="695" alt="image" src="https://github.com/user-attachments/assets/42ffa8a2-aae9-4e1b-9da0-3fd76813b228" />

ภาพที่ 7 Correlation Heatmap (แผนที่ความร้อนสหสัมพันธ์)</div>

ค่าสัมประสิทธิ์สหสัมพันธ์แบบเพียร์สัน (Pearson Correlation) ที่มีค่า มากกว่า 0.3 (ทั้งค่าบวกและลบ) หมายความว่ามีความสัมพันธ์เชิงเส้นระหว่างตัวแปรทั้งสองในระดับ ปานกลางถึงค่อนข้างมาก โดยมีค่าดังนี้
Married and BankCustomer = 0.992
PriorDefault and Approved = 0.720
Employed and CreditScore = 0.571
Employed and Approved = 0.458
PriorDefault and Employed = 0.432
CreditScore and Approved = 0.406
Age and YearsEmployed = 0.391
PriorDefault and CreditScore = 0.380
YearsEmployed and PriorDefault = 0.346
YearsEmployed and Approved = 0.322
YearsEmployed and CreditScore = 0.322
ZipCode and StateName = 0.302

<div align="center">
<img width="282" height="264" alt="image" src="https://github.com/user-attachments/assets/d6b1f9e7-3bed-43f6-9c50-cebd39ebe946" />

ภาพที่ 8 ค่าสัมประสิทธิ์สหสัมพันธ์แบบเพียร์สัน (Pearson Correlation) ที่มีค่า มากกว่า 0.3</div>

<div align="center">
<img width="769" height="300" alt="image" src="https://github.com/user-attachments/assets/ea279784-19f0-419a-ae23-fbd6a3e45645" />
 
ภาพที่ 9 ค่าสัมประสิทธิ์สหสัมพันธ์แบบเพียร์สัน (Pearson Correlation) ที่มีสัมพันธ์กับการอนุมัติสินเชื่อ</div>

บทสรุปเชิงวิเคราะห์: ปัจจัยด้าน ประวัติความเสี่ยง (PriorDefault) และ ความมั่นคง (Employed, CreditScore, YearsEmployed) เป็นคุณลักษณะหลักที่ขับเคลื่อนผลการตัดสินใจอนุมัติบัตรเครดิต ซึ่งตอบคำถามเชิงวิเคราะห์ที่ว่า "คุณลักษณะใดของผู้สมัครมีความสัมพันธ์กับการอนุมัติมากที่สุด"

4.3 Segmentation approach: การจัดกลุ่มลูกค้าตามโปรไฟล์ความเสี่ยง (Risk Profiles)
การเปรียบเทียบ Credit Score (CreditScore) ระหว่างผู้ที่ได้รับการอนุมัติ (Approved=1) และผู้ที่ไม่ได้รับการอนุมัติ (Approved=0) สามารถทำ t-test ได้ เนื่องจาก CreditScore เป็นตัวแปรเชิงปริมาณ(Numerical/ Continuous) และเราต้องการเปรียบเทียบค่าเฉลี่ยของตัวแปรนี้ระหว่างสองกลุ่มอิสระ(Approved=1 และ Approved=0) การใช้ Independent Samples T-test (การทดสอบทีสำหรับกลุ่มตัวอย่างอิสระ) จึงเป็นวิธีที่เหมาะสมที่สุด

<div align="center">
<img width="758" height="339" alt="image" src="https://github.com/user-attachments/assets/73440f04-5b1a-4b31-8cdf-598bd8d5b940" />

 ภาพที่ 10 Independent Samples T-test</div>

ผลจากการวิเคราะห์ความสัมพันธ์ของฟีเจอร์ (Correlation Analysis) เป็นไปตามสมมติฐานที่ว่ามีกลุ่มลูกค้า(Segments) ที่มีความเสี่ยงสูง/ต่ำ ที่แตกต่างกันชัดเจนหรือไม่ กล่าวโดยสรุปคือ ค่าเฉลี่ย Credit Score ของผู้ที่ได้รับการอนุมิติ แตกต่าง จากผู้ที่ไม่ได้รับการอนุมัติ

ข้อบกพร่องในเกณฑ์การตัดสินใจแบบเดิม (Potential Flaws in Traditional Criteria)
คำตอบ: หากเกณฑ์การตัดสินใจพึ่งพา CreditScore เพียงอย่างเดียวหรือใช้ค่า Cutoff ที่ไม่ยืดหยุ่น อาจเกิดข้อบกพร่องดังต่อไปนี้
ข้อบกพร่องที่อาจเกิดขึ้น	นัยยะทางธุรกิจ
การพึ่งพาตัวแปรเดียวมากเกินไป (Over-reliance on CreditScore)		อาจละเลยศักยภาพของลูกค้าที่มี CreditScore ปานกลาง (Gray Zone) แต่มีปัจจัยชดเชยอื่น ๆ ที่แข็งแกร่ง (เช่น Income สูงมาก หรือ YearsEmployed ยาวนาน) ซึ่งอาจกลายเป็นลูกค้าที่ดีในอนาคต
การใช้ค่า Cutoff แบบแข็งตัว	การใช้ค่า Cutoff แบบตายตัวอาจทำให้เสียโอกาส (Lost Opportunities) ในการอนุมัติลูกค้าที่เพิ่งผ่านเกณฑ์มาเพียงเล็กน้อย หรือปฏิเสธลูกค้าที่อยู่ต่ำกว่าเกณฑ์นิดเดียวแต่มีความเสี่ยงต่ำเมื่อรวมปัจจัยอื่น
การไม่พิจารณา Interaction Effects	เกณฑ์แบบเดิมอาจไม่ได้ให้ความสำคัญกับการทำงานร่วมกันของปัจจัย (เช่น ลูกค้าที่มี CreditScore ต่ำ แต่มีประวัติการจ้างงานมั่นคงยาวนาน) ทำให้การตัดสินใจขาดความแม่นยำในกลุ่มลูกค้าที่ซับซ้อน

5. Modeling Methodology

5.1 Model Development
- Algorithm selection: Classification Algorithms: Logistic Regression
- Training, hyperparameter tuning, evaluation metric: 
Training: แบ่งข้อมูลเป็น Training, Validation และ Test Sets (Cross-Validation) Tuning: Grid Search เพื่อหา Hyperparameters ที่เหมาะสมที่สุด
- Evaluation Metric: Accuracy, Precision, Recall, F1-Score

5.2 Workflow– Model Development

<div align="center">
<img width="1950" height="826" alt="image" src="https://github.com/user-attachments/assets/8b21aae2-6376-41b0-aab3-fcda7cf18d41" />

ภาพที่ 11 Logistic Regression </div>

5.3 Workflow– Model Development (Parameter Tuning / Hyperparameter Tuning)

<div align="center">
<img width="1573" height="602" alt="image" src="https://github.com/user-attachments/assets/1dbd4d3b-f822-4ce2-9576-c728daacd1ed" />

ภาพที่ 12 Logistic Regression with Parameter Tuning / Hyperparameter Tuning</div>

5.4 Workflow– Model Development (Parameter Tuning / Hyperparameter Tuning with Pipeline and GridsearchCV)

<div align="center">
<img width="1722" height="684" alt="image" src="https://github.com/user-attachments/assets/329bf0e2-4139-4b4b-8fb0-54309c143168" />
<img width="2185" height="686" alt="image" src="https://github.com/user-attachments/assets/dc67dc21-f613-406a-bad5-fa0cda4cc62e" />

ภาพที่ 13 Logistic Regression with Parameter Tuning / Hyperparameter Tuning with Pipeline and GridsearchCV</div>


5.5 Model Evaluation
 
ประสิทธิภาพและการทำงานของแบบจำลอง (Model Performance and Discussion)
ผลลัพธ์จากโมเดลการพยากรณ์นี้แสดงให้เห็นว่าโมเดลมีความสามารถในการจำแนกผู้ขอสินเชื่อบัตรเครดิตได้อย่างแม่นยำและสมดุล โดยมี Accuracy รวมอยู่ที่ 88% จาก 173 ตัวอย่างในชุดทดสอบ ซึ่งสูงกว่าเกณฑ์ที่ยอมรับได้สำหรับงานจำแนกประเภท

<div align="center">
<img width="1858" height="608" alt="image" src="https://github.com/user-attachments/assets/46812181-8b15-47ea-a638-5609f3f556aa" />

ภาพที่ 14 Model Evaluation with Confusion Matrix

<img width="712" height="243" alt="image" src="https://github.com/user-attachments/assets/c597ca7e-5c0f-4d50-ab4e-daa21c2423cc" />

<img width="713" height="225" alt="image" src="https://github.com/user-attachments/assets/1b4c027a-a1ee-4af9-a091-210af6404da6" />

ภาพที่ 15 Model Evaluation with Report</div>
 
โมเดลนี้มีประสิทธิภาพดีและสามารถนำไป Deploy เพื่อใช้ในการตัดสินใจอนุมัติเบื้องต้นโดยอัตโนมัติได้ตาม Value Proposition ของโครงการ อย่างไรก็ตาม ควรเน้นการปรับปรุง Precision ของ Class 1 ให้สูงขึ้นเพื่อลดความเสี่ยงหนี้เสีย (FP) ให้สอดคล้องกับวัตถุประสงค์ทางธุรกิจหลักของสถาบันการเงิน


6. Findings and Business Insights

คุณลักษณะหลักที่ขับเคลื่อนผลการอนุมัติบัตรเครดิต (Feature Importance) คือ ปัจจัยด้าน ประวัติความเสี่ยง (PriorDefault) และ ความมั่นคง (Employed, CreditScore, YearsEmployed) โดยสามารถ ระบุกลุ่มลูกค้าที่มีความเสี่ยงสูง/ต่ำ ที่ชัดเจนได้โดย Credit Score ซึ่งเป็นปัจจัยขับเคลื่อนหลัก (Primary Driver) ในกระบวนการอนุมัติ ทำให้เกิดการแบ่งกลุ่มลูกค้าเป็นสองกลุ่มได้อย่างมีประสิทธิภาพ 
ดังนั้นแนวโน้มและรูปแบบคุณลักษณะของผู้สมัครที่ถูกอนุมัติ/ปฏิเสธ คือ ประวัติความเสี่ยง (PriorDefault) และ ความมั่นคง (Employed, CreditScore, YearsEmployed) เป็นคุณลักษณะหลักที่ขับเคลื่อนผลการตัดสินใจอนุมัติบัตรเครดิต ซึ่งตอบคำถามเชิงวิเคราะห์ที่ว่า "คุณลักษณะใดของผู้สมัครมีความสัมพันธ์กับการอนุมัติมากที่สุด"
จากการเปรียบเทียบ Credit Score (CreditScore) ระหว่างผู้ที่ได้รับการอนุมัติ (Approved=1) และผู้ที่ไม่ได้รับการอนุมัติ (Approved=0) ค่าเฉลี่ย Credit Score ของผู้ที่ได้รับการอนุมิติ แตกต่าง จากผู้ที่ไม่ได้รับการอนุมัติ ซึ่งตอบคำถามเชิงวิเคราะห์ที่ว่า “มีกลุ่มลูกค้า (Segments) ที่มีความเสี่ยงสูง/ต่ำ ที่แตกต่างกันชัดเจนหรือไม่”
	อย่างไรก็ตาม หากเกณฑ์การตัดสินใจพึ่งพา CreditScore เพียงอย่างเดียวหรือใช้ค่า Cutoff ที่ไม่ยืดหยุ่น อาจเกิดข้อบกพร่องดังต่อไปนี้ 1. การพึ่งพาตัวแปรเดียวมากเกินไป (Over-reliance on CreditScore) 2. การใช้ค่า Cutoff แบบแข็งตัว 3. การไม่พิจารณา Interaction Effects ดังนั้นการพัฒนาโมเดลทำนายผลการอนุมัติบัตรเครดิต (Approved หรือ Rejected) จากข้อมูลของผู้สมัครที่ให้มาด้วยความแม่นยำสูง เพื่อช่วยในการตัดสินใจอัตโนมัติ โดยใช้ปัจจจัยอื่นๆ ร่วมด้วย ทำให้โมเดลการพยากรณ์นี้มีความสามารถในการจำแนกผู้ขอสินเชื่อบัตรเครดิตได้อย่างแม่นยำและสมดุล โดยมี Accuracy รวมอยู่ที่ 88% จาก 173 ตัวอย่างในชุดทดสอบ ซึ่งสูงกว่าเกณฑ์ที่ยอมรับได้สำหรับงานจำแนกประเภท

7. Conclusion and Recommendation
   
จากการวิเคราะห์ที่กล่าวมา จะทำให้เราทราบถึงปัจจัยสำคัญที่นำมาวิเคราะห์การอนุมัติสินเชื่อที่เหมาะสมรวมถึงการสร้างแบบจำลองเพื่อทำนายผลการอนุมัติบัตรเครดิตโดยอัตโนมัติ เพื่อเพิ่มความรวดเร็วและความแม่นยำในการตัดสินใจ และการลดความเสี่ยงทางการเงิน (อัตราการผิดนัดชำระหนี้ - Default Rate) รวมถึงเพิ่มประสิทธิภาพในการดำเนินงาน (Operational Efficiency) ของฝ่ายอนุมัติสินเชื่อของธนาคารและสถาบันการเงิน (ฝ่ายบริหารความเสี่ยง, ฝ่ายการตลาด, ฝ่ายปฏิบัติการ) โดยที่โมเดลนี้สามารถให้ผลการตัดสินใจเบื้องต้นที่ รวดเร็ว (Operational Impact) และ เป็นกลาง ด้วย Accuracy 88% และทำให้ลดการเกิดหนี้เสีย (ลดความเสี่ยง) เนื่องจากมีความแม่นยำในการคัดกรองมากขึ้น และเพิ่มโอกาสในการอนุมัติลูกค้าที่มีคุณภาพเร็วขึ้น (เพิ่มกำไร) และผู้สมัครได้รับผลการตัดสินใจรวดเร็วขึ้น ทำให้ประสบการณ์การใช้บริการดีขึ้น



