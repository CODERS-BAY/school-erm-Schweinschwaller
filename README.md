# SchoolERM
A school information system for an HTL is to be developed:
The departmental structure of an HTL is to be reproduced. Each teacher is assigned to a department as a master department, but can also teach in classes of other departments. Each department is headed by a teacher as head of department.
For each form of education of the departments, the curriculum specifies which subjects have to be taught in which year and to what extent (theory and practice lessons).
The classes of a school year are taught by the teachers in the individual subjects to a certain extent (theory and practice lessons). Each student is assessed with one semester and one year mark per class and subject. The system should be able to record this information for several school years.
It should be possible to find out the class leaders of the different classes, as well as by whom which functions (class representative, cashier, etc.) are or were exercised.
Teachers are not remunerated according to the number of hours they teach, but according to the value units they hold: Each subject is assigned to a specific compulsory teaching group (I to VI). A factor (1.167 to 0.75) is defined for each teaching obligation group, which is used to convert lessons into value units.
A parent is responsible for each pupil (unless the pupil is a self-entitled guardian). If siblings attend school, this should also be able to be determined.


---

Department(<ins>name:varchar</ins>, headteacher:varchar, teacher:varchar, subjects:varchar)<br>
Curriculum(<ins>ID:int</ins>, year:int, departmentname:varchar, subjects:varchar)<br>
Subject(<ins>ID:int</ins>, name:varchar, teacher:varchar, room:varchar, obligationGroup:int, factor:double, kind:boolean)<br>
class(<ins>ID:int</ins>, name:varchar, year:int, departmentname:varchar, headteacher:varchar, respresentative:varchar, cashier:varchar)<br>
Parents(<ins>SVR:int</ins>, name:varchar, adresse:varchar, tel:varchar, birthday:timestamp)<br>
Student(<ins>SVR:int</ins>, name:varchar, adresse:varchar, tel:varchar, marks:int, siblings:varchar, birthday:timestamp)<br>
Teacher(<ins>SVR:int</ins>, masterDepartmend:varchar, subjects:varchar, class:varchar, birthday:timestamp)<br>
teach(<ins>year:int</ins>, studentSVR:int, semesterMark:int, yearMark:in)<br>
