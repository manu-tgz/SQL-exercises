# Create database and tables

### Create database 

```
CREATE DATABASE faculty
```

### Create student table
```
CREATE TABLE student
(   st_id char(5) PRIMARY KEY,
    name char(40) NOT NULL ,
    student_group char(6),
    province char(25) NOT NULL
)
```
### Create student subject
```
CREATE TABLE subject
(   s_id char(4) PRIMARY KEY,
    name char(25) NOT NULL,
    hours smallint DEFAULT 90
)
```
### Create student qualification
```
CREATE TABLE qualification
(
st_id char(5),
s_id char(4) ,
qualification smallint NOT NULL,
PRIMARY KEY(st_id, s_id),
FOREIGN KEY(st_id) REFERENCES student(st_id) 
                         ON DELETE RESTRICT
                         ON UPDATE CASCADE,

FOREIGN KEY(s_id) REFERENCES subject(s_id)
                         ON DELETE RESTRICT
                         ON UPDATE CASCADE, 

CHECK(qualification>=18 AND qualification<=30)
)
```
# DB Population
# Exercises