


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
  - [Run tests](#run-tests)
  - [Deployment](#triangular_flag_on_post-deployment)
- [👥 Authors](#authors)
- [🔭 Future Features](#future-features)
- [🤝 Contributing](#contributing)
- [⭐️ Show your support](#support)
- [🙏 Acknowledgements](#acknowledgements)
- [❓ FAQ (OPTIONAL)](#faq)
  
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
<!--
  

--->
### Install
Install this project with:
<!--Provision Database: Create a new project instance within the Supabase dashboard.

Locate Script: The full database schema and sample data are contained in the schema.sql file.

--->
### Usage
To run the project, execute the following command:
<!-- --output query
--<img width="1240" height="583" alt="image" src="https://github.com/user-attachments/assets/502fd739-0157-443c-8aa5-c91332db88d7" />

<img width="1357" height="647" alt="image" src="https://github.com/user-attachments/assets/81eb1212-af23-464d-9fdf-21532985bd8e" />

<img width="1216" height="670" alt="image" src="https://github.com/user-attachments/assets/2a56eca4-138b-4cf3-9d49-040a178846bb" />


`
``To initialize the database schema and populate it with sample data:

Navigate to the SQL Editor within your Supabase project dashboard.
Example command:
```sh
  
`
``
--->
### Run tests
To run tests, run the following command:
<!--
Example command:-- Test Query: Verifies FK links by combining student, course, and enrollment data.
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
You can deploy this project using:
<!--supabase
Example:
```sh
```
 -->
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- AUTHORS -->
## 👥 Authors <a name="authors"></a>
> Mention all of the collaborators of this project.
👤 **Author1**
- GitHub: [@githubhandle](https://github.com/githubhandle)
- Twitter: [@twitterhandle](https://twitter.com/twitterhandle)
- LinkedIn: [LinkedIn](https://linkedin.com/in/linkedinhandle)
👤 **Author2**
- GitHub: [@githubhandle](https://github.com/githubhandle)
- Twitter: [@twitterhandle](https://twitter.com/twitterhandle)
- LinkedIn: [LinkedIn](https://linkedin.com/in/linkedinhandle)
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- FUTURE FEATURES -->
## 🔭 Future Features <a name="future-features"></a>
> Describe 1 - 3 features you will add to the project.
- [ ] **[new_feature_1]**
- [ ] **[new_feature_2]**
- [ ] **[new_feature_3]**
<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- CONTRIBUTING -->
## 🤝 Contributing <a name="contributing"></a>
Contributions, issues, and feature requests are welcome!
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

## ❓ FAQ (OPTIONAL) <a name="faq"></a>
> Add at least 2 questions new developers would ask when they decide to use your project.
- **[Why is enrollment aseparate table?]**
  - [This is necessary because the relationship between students and courses is Many-to-Many (one student takes many courses, and one course has many students). The enrollments table acts as a junction to manage this relationship.]
- **How can i see a student's full course load?]**
  - [ You must use a 3-table JOIN query between students, courses, and enrollments, linked by their respective IDs.]
<p align="right">(<a href="#readme-top">back to top</a>)</p>

0 commit comments
Comments


