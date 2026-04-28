# Performance Testing

## Test Plan 1 (/all-student)
1. View Results Tree
   ![all-student view results tree](/assets/images/test_plan_1 results tree.png)
2. View Results in Table
   ![all-student view results in table](/assets/images/test_plan_1 results in table.png)
3. Summary Report
   ![all-student summary report](/assets/images/test_plan_1 summary report.png)
4. Graph Results
   ![all-student graph results](/assets/images/test_plan_1 graph results.png)
5. CLI
   ![all-student cli results](/assets/images/test_plan_1 cli.png)
6. After Optimizing
   ![all-student after optimizing](/assets/images/all-student after optimizing.png)


## Test Plan 2 (/all-student-name)
1. View Results Tree
   ![all-student-name view results tree](/assets/images/test_plan_2 results tree.png)
2. View Results in Table
   ![all-student-name view results in table](/assets/images/test_plan_2 results in table.png)
3. Summary Report
   ![all-student-name summary report](/assets/images/test_plan_2 summary report.png)
4. Graph Results
   ![all-student-name graph results](/assets/images/test_plan_2 graph results.png)
5. CLI
   ![all-student-name cli results](/assets/images/test_plan_2 cli.png)
6. After Optimizing
   ![all-student-name after optimizing](/assets/images/all-student-name after optimizing.png)


## Test Plan 3 (/highest-gpa)
1. View Results Tree
   ![highest-gpa view results tree](/assets/images/test_plan_3 results tree.png)
2. View Results in Table
   ![highest-gpa view results in table](/assets/images/test_plan_3 results in table.png)
3. Summary Report
   ![highest-gpa summary report](/assets/images/test_plan_3 summary report.png)
4. Graph Results
   ![highest-gpa graph results](/assets/images/test_plan_3 graph results.png)
5. CLI
   ![highest-gpa cli results](/assets/images/test_plan_3 cli.png)
6. After Optimizing
   ![highest-gpa after optimizing](/assets/images/highest-gpa after optimizing.png)


## Hasil Performance Testing After Optimizing

Hasil performance testing menunjukkan adanya peningkatan performance pada seluruh endpoint yang ditest.

- Endpoint `/all-student` mengalami penurunan response time dari yang average-nya 57751 menjadi 21641.
- Endpoint `/all-student-name` mengalami penurunan response time dari yang average-nya 1005 menjadi 303.
- Endpoint `/highest-gpa` mengalami penurunan response time dari yang average-nya 440 menjadi 152.

Dapat disimpulkan bahwa optimization yang dilakukan berhasil meningkatkan performance aplikasi, yang ditandai dengan penurunan response time dibandingkan sebelum optimization.


# Performance Optimization
1. /all-student
   ![cpu time getallstudentswithcourses](/assets/images/cpu time getallstudentswithcourses.png)
2. /all-student-names
   ![cpu time joinstudentnames](/assets/images/cpu time joinstudentnames.png)
3. /highest-gpa
   ![cpu time findstudentwithhighestgpa](/assets/images/cpu time findstudentwithhighestgpa.png)