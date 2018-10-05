# <Asgn-5-1>

<br />I think that based on the fact that students want to get more information about the courses and they are tired
of checking whether a course has empty space several times a day online, I want to design a software that could
test students about the course information when they are allowed to choose course.
<br />When students are allowed to choose courses, they will receive a text message giving them a list of recommended
courses based on their years and previous courses. Thus, students can use that information along with the adviceds
from their advisors/parents/friends to find the courses that they fit most.
<br />On the Vanderbilt's course selection system, students can mark a now fully filled course as "Interested".
Thus, whenever that course has available empty spaces, students will receive a text message about that. In this
way, students do not have to check course avalability online several times a day.

# Questions:
  1. Where do you get advice about choosing which course to take?
  2. How often do you use Vanderbilt's Student Registration?
  3. Do you think it is hard to find a course using Student Registration?
  4. How do you get information about a course?
  5. What kind of information you want to find on Vanderbilt course selection system?
  6. Can you always get enrolled in the course you want to?
  7. If Vanderbilt's course selection system offers a list of recommended course, to what extent will you trust it?
  8. How do you know that a course you are interested about now has empty spaces?
  9. Are you satisfied with the UI Vanderbilt's course selection system?
  10. What kind of new features you want to see at Vanderbilt's course selection system?

## Question 1: 
<br />From interviewer1: Mostly from advisor
<br />From interviewer2: From advisor and senior students
<br />From interviewer3: From advisor parents

## Question 2:
<br />From interviewer1: Only used during course selection times
<br />From interviewer2: Won't use it anymore after selecting courses
<br />From interviewer3: May check occassionally for new course information

## Question 3:
<br />From interviewer1: Yes, sometimes event I entered the correct course number, it still not shows the course I want
<br />From interviewer2: Yes, it is pretty hard.
<br />From interviewer3: Yes, it takes time to find a course I want

## Question 4:
<br />From interviewer1: From senior students
<br />From interviewer2: Using some external websites like "Rate my professor"
<br />From interviewer3: Asking advices from parents

## Question 5:
<br />From interviewer1: I want to know the difficulty of the course
<br />From interviewer2: I want to knwo how other people think this professor
<br />From interviewer3: I want to get the syllabus beforehead

## Question 6:
<br />From interviewer1: No, I may need to wait for 1 or 2 semesters to get into the course I want
<br />From interviewer2: No.
<br />From interviewer3: No, sometimes some courses are full

## Question 7:
<br />From interviewer1: Kind of trust, I will compare it with the courses I want to take in my mind.
<br />From interviewer2: Kind of, if it did a good performace in one semester, I will trust it afterwards.
<br />From interviewer3: I will fully trust the technology.

## Question 8:
<br />From interviewer1: By checking that course several times a day.
<br />From interviewer2: By checking that course online or my friends will tell me.
<br />From interviewer3: By checking online

## Question 9:
<br />From interviewer1: No, it't not pretty enough
<br />From interviewer2: No, it can not provide the information I want
<br />From interviewer3: I am kind of satisfied

## Question 10:
<br />From interviewer1: The recommended courses
<br />From interviewer2: The course difficulty
<br />From interviewer3: The course syllabus

# Requirements
<br />The overall requirement for my application is to build an application that could send text messages to students 
when they have access to enroll courses. The background is that students can't get much help from the course enrollment 
system and students have to often check online to see whether their deisred courses have openings. From the product perspective,
we may need to store the data about all students with their recommended courses in the database. If one database can not
support all the data, we need to get several databases to shard all the data. And since we only want to send text messages
to students at certain times, we also need constraints on the sending process. 

# Development Approach
<br /> When developing this software, it is desirable to design it from the backend to the frontend. For the backend,
we may use the MySQl database to store all the user data and the courses as well as the performance on thoses courses.
After that, we could use machine learning model to analysis thoses courses and based on those data, get a result of
the recommended courses. After we get the recommended courses of each student, we could use a schedule pattern to 
make sure we send the recommended courses at the right time. Since this data may become huge, we may need to store it 
all different databases. We could use hashing based on the student id to determine which database to store the student
data. After we finished about the back end part, we could build the front end part such as what is the exact message we 
want to send. After all thoses things is built, we could first test on only a small part of students, if everything is 
fine, we can use all students.