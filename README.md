# District Analysis Update

## Overview
Thanks to purported academic dishonesty from the Thomas High School 9th Grade students, this analysis update is designed to analyze the changes in the overall district analysis after replacing those grades with NaN grades (Not a Number, or Not Applicable).

## Thomas High School 9th Grade
### Characteristics
Here are some characteristics of Thomas High School and the 9th grade that will be the main sections changing as we go through the grade adjustment:
- Thomas High School has 1635 students, of which 461 are in the 9th grade.
- Thomas High School is a Charter school.
- Thomas High School has a budget of $638.00 per student.
We can therefore expect those categories to be changed, while other categories remain mostly the same.

## Removal of Thomas High School 9th Grade Scores
Removal of Thomas High School 9th grade scores was accomplished by using the .loc[] method to isolate only the math or reading scores of 9th grade Thomas HS students and replace them with 'NaN'.  A sample of this conditional is below:
```
student_data_df.loc[(student_data_df['grade'] == '9th') &
                    (student_data_df['school_name'] == 'Thomas High School'), ['reading_score']] = np.NaN
```

## Effects of Removing the Offending Grades

### District Summary
#### Original
![Original District Summary](/Images/DistrictSummaryModule.png)
#### Updated
![Updated District Summary](/Images/DistrictSummary.png)
#### Analysis
The only change in the district summary would be the change in math, reading, and overall passing percentages, which dropped 0.2%, 0.1%, and 0.2% respectively with the removal of the offending grades.

### School Summary
#### Original
![Original School Summary](/Images/SchoolSummaryModule.png)
#### Updated
![Updated School Summary](/Images/SchoolSummary.png)
#### Analysis


### Thomas High School Performance
#### Original
![Original Thomas HS Performance](/Images/ThomasOldData.png)
#### Updated
![Updated Thomas HS Performance Compared to Top Schools](/Images/ThomasNewDataHead.png)
#### Analysis

### Math and Reading Scores by Grade
#### Original Math
![Original Math Scores by Grade](/Images/MathbyGradeModule.png)
#### Updated Math
![Updated Math Scores by Grade](/Images/MathbyGrade.png)
#### Original Reading
![Original Reading Scores by Grade](/Images/ReadingbyGradeModule.png)
#### Updated Reading
![Updated Reading Scores by Grade](/Images/ReadingbyGrade.png)
#### Analysis

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

### Scores by School Type
#### Original
![Original Scores by School Type](/Images/ScoresbyTypeModule.png)
#### Updated
![Updated Scores by School Type](/Images/ScoresbyType.png)
#### Analysis

## Summary
