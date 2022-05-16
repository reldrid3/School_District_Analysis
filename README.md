# District Analysis Update

## Overview
Thanks to purported academic dishonesty from the Thomas High School 9th Grade students, this analysis update is designed to analyze the changes in the overall district analysis after replacing those grades with NaN grades (Not a Number, or Not Applicable).

## Thomas High School 9th Grade
### Characteristics
Here are some characteristics of Thomas High School and the 9th grade that will be the main sections changing as we go through the grade adjustment:
- Thomas High School has 1635 students, of which 461 are in the 9th grade and 1174 are in grades 10-12.
- Thomas High School is a Charter school.
- Thomas High School has a budget of $638.00 per student.
We can therefore expect those categories to be changed, while other categories remain mostly the same.

## Removal of Thomas High School 9th Grade Scores
Removal of Thomas High School 9th grade scores was accomplished by using the .loc[] method to isolate only the math or reading scores of 9th grade Thomas HS students and replace them with 'NaN'.  A sample of this conditional is below:
```
student_data_df.loc[(student_data_df['grade'] == '9th') &
                    (student_data_df['school_name'] == 'Thomas High School'), ['reading_score']] = np.NaN
```
One important change that needed to be made when calculating the overall passing percentages was using only the 10th-12th grade student population as the denominator, as calculating it with the full student body would drastically reduce the passing rate.

## Effects of Removing the Offending Grades

### District Summary
#### Original
![Original District Summary](/Images/DistrictSummaryModule.png)
#### Updated
![Updated District Summary](/Images/DistrictSummary.png)
#### Analysis
The only change in the district summary would be the change in math, reading, and overall passing percentages, which dropped 0.2%, 0.1%, and 0.2% respectively with the removal of the offending grades.

### School Summary - Thomas High School Performance
#### Original
![Original Thomas HS Performance](/Images/ThomasOldDataModule.png)
#### Incorrect
![Thomas HS Performance without Recalibrating](/Images/ThomasOldData.png)
#### Updated
![Updated Thomas HS Performance Compared to Top Schools](/Images/ThomasNewDataHead.png)
#### Analysis
Instead of looking at the entire school summary, I will be comparing only Thomas's data, as well as its rank to a few other top schools.  As you can see, the math and reading scores, as well as the passing percentages did change from the original data, but only slightly - the overall passing rate dropped by approximately 0.3%.  Reading score averages even went up, though passing rates went down (this is easily possible since the average is not equal to the passing rate of 70%).

If you look at the center "Incorrect" diagram, the passing percentages are far lower, as we were still dividing the passing scores by 1635, instead of 1174 after removing all of the 9th grade scores.  You can even see that the numbers differ by a factor of 1635/1174, or 1.39267.  For example, looking at math passing percentages, 66.911315 * 1.392674617 = 93.185690.

Thomas HS had been the #2 overall passing school in the district, and even after removing the 9th grade's scores, it still remains as successful.

### Math and Reading Scores by Grade
#### Math Scores by Grade
| Original Math Scores | Updated Math Scores |
| --- | --- |
| ![Original Math Scores by Grade](/Images/MathbyGradeModule.png) | ![Updated Math Scores by Grade](/Images/MathbyGrade.png) |
#### Reading Score by Grade
| Original Reading Scores | Updated Reading Scores |
| --- | --- |
| ![Original Reading Scores by Grade](/Images/ReadingbyGradeModule.png) | ![Updated Reading Scores by Grade](/Images/ReadingbyGrade.png) |
#### Analysis
As can be expected, no other grades' scores were adjusted other than Thomas High School's 9th grade, which now has "nan" as its score average.

### Scores by School Spending per Student
#### Original
![Original Scores by School Spending per Student](/Images/PerStudentSpendingModule.png)
#### Updated
![Updated Scores by School Spending per Student](/Images/PerStudentSpending.png)
#### Analysis


### Scores by School Size
#### Original
![Original Scores by School Size](/Images/ScoresbySizeModule.png)
#### Updated
![Updated Scores by School Size](/Images/ScoresbySize.png)
#### Analysis
I adjusted the bins for the schools, but the 1000-1999 bin remained the same in this case.  The original data was rounded to the nearest 1%, while my data is more accurate, and while it doesn't show any inherent difference based on rounding error, it's likely that the difference in the passing percentages is in the 0.1-0.3% range.

### Scores by School Type
#### Original
![Original Scores by School Type](/Images/ScoresbyTypeModule.png)
#### Updated
![Updated Scores by School Type](/Images/ScoresbyType.png)
#### Analysis
Much like scores by school size, the difference is so small that rounding error is enough to encompass a likely 0.1-0.3% change in the passing rates of the Charter group of schools.

## Summary
