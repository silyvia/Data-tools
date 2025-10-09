


<!-- TABLE OF CONTENTS -->
# 📗 Table of Contents
- [📖 About the Project](#about-project)
  - [🛠 Built With](#built-with)
    - [Tech Stack](#tech-stack)
    - [Key Features](#key-features
- [💻 Getting Started](#getting-started)
  - [Setup](#setup)
  - [Prerequisites](#prerequisites)
  - [Install](#install)
  - [Usage](#usage)
  - ERD Diagram.
  - Schema SQL
  - [Run tests](#run-tests)
  - [Deployment](#triangular_flag_on_post-deployment)
- [👥 Authors](#authors)
- [🔭 Future Features](#future-features)
- [🤝 Contributing](#contributing)
- [⭐️ Show your support](#support)
- [🙏 Acknowledgements](#acknowledgements)
  
  
<!-- PROJECT DESCRIPTION -->
# 📖 [Data tools final project-E-learning platform data base] <a name="about-project"></a>
>The project established the relationaldatabase foundation for a digital E-learning platform,successfully modeling the relationship between students,available courses and their records of enrolment .
**[E-learning platform i]** is a fullyfunctional three-table relational data schema.
## 🛠 Built With <a name="built-with"></a>
### Tech Stack <a name="tech-stack"></a>
> The project utilized a standard open-source data stack to ensure portability and stability.

    <li><a href="https://supabase.io/">Supabase</a>(PostgreSQL hosting)</li>
  </ul>
</detais>
<details>
  <summary>Language</summary>
  <ul>
    <li><a href="https://expressjs.com/">SQL</a></li>
  </ul>
</details>
<details>
<summary>Database</summary>
  <ul>
    <li><a href="https://www.postgresql.org/">PostgreSQL</a></li>
  </ul>
</details>
<!-- Features -->
### Key Features <a name="key-features"></a>
> Describe between 1-3 key features of the application.
- **[Many-to-Many Enrollment: Successfully implemented the Many-to-Many relationship between students and courses using the enrollments junction table. This allows a student to take multiple courses and a course to have multiple students.]**
- **[Data Integrity via Foreign Keys: Defined two mandatory Foreign Keys in the enrollments table (student_id and course_id) to ensure that every enrollment record links to existing, valid student and course entries.]**
- **[Sample Data Population: Populated all three tables (students, courses, and enrollments) with six rows of sample data each, providing a functional dataset for Week 2 analysis.]**
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## 💻 Getting Started <a name="getting-started"></a>
> To demonstrate the project's setup,follow these steps to recreate database structure and data.

### Prerequisites
In order to run this project you need:
<--A supabase account>
<```Basic knowledge of SQL commands:>

<```The schema.sql file.>

 -->
### Setup
<```clone this resipitory:>
<```https://github.com/silyvia?tab=repositories>
  

--->
### Install
Install this project with:
<```Provision Database: Create a new project instance within the Supabase dashboard.>

<```Locate Script: The full database schema and sample data are contained in the schema.sql file.>

--->
### Usage
To run the project, execute the following command:
```sql
-- E-learning Platform Database Schema (Week 1)
-- Tables: students, courses, enrollments

-- 1. Create the students Table
-- Stores user/student profile data.
CREATE TABLE public.students (
    student_id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    student_name TEXT NOT NULL,
    email TEXT UNIQUE NOT NULL,
    major TEXT, -- e.g., 'Computer Science', 'Data Analytics'
    registration_date DATE DEFAULT CURRENT_DATE
);

-- Insert 6 rows of sample student data
INSERT INTO public.students (student_name, email, major)
VALUES 
    ('Sarah Kamau', 'sarah.k@email.com', 'Data Analytics'),
    ('David Omondi', 'david.o@email.com', 'Web Development'),
    ('Aisha Gichuru', 'aisha.g@email.com', 'Marketing'),
    ('John Mburu', 'john.m@email.com', 'Computer Science'),
    ('Emily Wanjiku', 'emily.w@email.com', 'Data Analytics'),
    ('Peter Ndungâ€™u', 'peter.n@email.com', 'Web Development');


-- 2. Create the courses Table
-- Stores the course catalog.
CREATE TABLE public.courses (
    course_id INT PRIMARY KEY,
    course_name TEXT UNIQUE NOT NULL, -- e.g., 'Intro to SQL', 'Advanced Python'
    instructor TEXT NOT NULL,
    credits NUMERIC(2, 1) -- Course credit hours (e.g., 3.0)
);

-- Insert 6 rows of sample course data
INSERT INTO public.courses (course_id, course_name, instructor, credits)
VALUES 
    (101, 'Introduction to SQL', 'Dr. Mwangi', 3.0),
    (102, 'Data Modeling Fundamentals', 'Prof. Adisa', 4.0),
    (103, 'Python for Beginners', 'Ms. Chepkoech', 3.0),
    (104, 'Cloud Computing Basics', 'Mr. Kioko', 2.0),
    (105, 'Web Design Principles', 'Dr. Mwangi', 3.0),
    (106, 'Advanced Data Visualization', 'Prof. Adisa', 4.0);


-- 3. Create the enrollments Table (The central linking table)
-- Records which student is taking which course.
CREATE TABLE public.enrollments (
    enrollment_id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    
    -- FOREIGN KEY 1: Links to the student
    student_id UUID REFERENCES public.students(student_id) ON DELETE CASCADE, 
    
    -- FOREIGN KEY 2: Links to the course
    course_id INT REFERENCES public.courses(course_id) ON DELETE RESTRICT,
    
    enrollment_date DATE DEFAULT CURRENT_DATE,
    grade_received TEXT -- e.g., 'A', 'B+', 'In Progress'
);

-- Insert 6 rows of sample enrollment data
INSERT INTO public.enrollments (student_id, course_id, grade_received)
VALUES 
    ((SELECT student_id FROM public.students WHERE student_name = 'Sarah Kamau'), (SELECT course_id FROM public.courses WHERE course_name = 'Data Modeling Fundamentals'), 'B+'),
    ((SELECT student_id FROM public.students WHERE student_name = 'David Omondi'), (SELECT course_id FROM public.courses WHERE course_name = 'Web Design Principles'), 'A'),
    ((SELECT student_id FROM public.students WHERE student_name = 'Aisha Gichuru'), (SELECT course_id FROM public.courses WHERE course_name = 'Introduction to SQL'), 'A-'),
    ((SELECT student_id FROM public.students WHERE student_name = 'John Mburu'), (SELECT course_id FROM public.courses WHERE course_name = 'Cloud Computing Basics'), 'In Progress'),
    ((SELECT student_id FROM public.students WHERE student_name = 'Sarah Kamau'), (SELECT course_id FROM public.courses WHERE course_name = 'Advanced Data Visualization'), 'B'),
    ((SELECT student_id FROM public.students WHERE student_name = 'Peter Ndungâ€™u'), (SELECT course_id FROM public.courses WHERE course_name = 'Python for Beginners'), 'In Progress');

   
```
###Output of the sql queries
```sql
 select * from students
```
**All students**
<img width="1576" height="705" alt="image" src="https://github.com/user-attachments/assets/a3beb5df-857a-4e94-9f0e-f6f24414a2ef" />

### ERD DIAGRAM

<img width="915" height="580" alt="image" src="https://github.com/user-attachments/assets/27028d25-16e1-44a5-b460-6e4e9e889933" />




`
<``To initialize the database schema and populate it with sample data:>

<``Navigate to the SQL Editor within your Supabase project dashboard.
Example command:
```sh
  
`
``
--->
### Run tests
<``To run tests, run the following command:>
<!--
<``Example command:-- Test Query: Verifies FK links by combining student, course, and enrollment data.>
SELECT
    s.student_name,         
    c.course_name,          
    e.grade_received        
FROM
    enrollments e 
JOIN
    students s ON e.student_id = s.student_id
JOIN
    courses c ON e.course_id = c.course_id
ORDER BY
    s.student_name;

<img width="1101" height="818" alt="image" src="https://github.com/user-attachments/assets/ba7f20c3-1c24-4ede-ab13-c6040a209edf" />





```
  bin/rails test test/models/article_test.rb
```
--->
### Deployment

<```You can deploy this project using:>
<--supabase>
Example:
```sh
```
 -->
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- AUTHORS -->
## 👥 Authors <Silyvia ongwae="authors"></a>
> Silyvia Ongwae
👤 **Author1**
- GitHub: [@githubhandle](https://github.com/silyvia/
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- FUTURE FEATURES -->
## 🔭 Future Features <a name="future-features"></a>

- **Application-level functionality**
-  **Status tracking management**

<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- CONTRIBUTING -->
## 🤝 Contributing <a name="contributing"></a>
<``Contributions, issues, and feature requests are welcome!>
Feel free to check the [issues page](../../issues/).
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- SUPPORT -->
## ⭐️ Show your support <a name="support"></a>
>If you find this schema useful for designing your E-learning applications,please give a repository star.
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- ACKNOWLEDGEMENTS -->
## 🙏 Acknowledgments <a name="acknowledgements"></a>
>I would like to thank my instructor and the Supabase team for providing the tools and guidance necessary for this project. 
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- 
  ## ❓FAQ (OPTIONAL) <a name="faq"></a>
> Add at least 2 questions new developers would ask when they decide to use your project.
- **Why is enrollment aseparate table?**
  <``This is necessary because the relationship between students and courses is Many-to-Many (one student takes many courses, and one course has many students). The enrollments table acts as a junction to manage this relationship.>
- **How can i see a student's full course load?]**
  - ** You must use a 3-table JOIN query between students, courses, and enrollments, linked by their respective IDs.
<p align="right">(<a href="#readme-top">back to top</a>)</p>



