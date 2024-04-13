NESTED QUERY 
SQL>create table student(id number(10), name varchar2(20),classID number(10), marks 
varchar2(20)); 
SQL>insert into student values(1,'pinky',3,2.4); 
SQL>insert into student values(2,'bob',3,1.44); 
SQL>insert into student values(3,'Jam',1,3.24); 
SQL>insert into student values(4,'lucky',2,2.67); 
SQL>insert into student values(5,'ram',2,4.56); 
SQL>select * from student; 
SQL>Create table teacher(id number(10), name varchar(20), subject varchar2(10), classID 
number(10), salary number(30)); 
SQL>insert into teacher values(1,’bhanu’,’computer’,3,5000); 
SQL>insert into teacher values(2,'rekha','science',1,5000); 
SQL>insert into teacher values(3,'siri','social',NULL,4500); 
SQL>insert into teacher values(4,'kittu','mathsr',2,5500); 
SQL>select * from teacher; 
Department of Computer Science and Engineering
SQL>Create table class(id number(10), grade number(10), teacherID number(10), 
noofstudents number(10)); 
SQL>insert into class values(1,8,2,20); 
SQL>insert into class values(2,9,3,40); 
SQL>insert into class values(3,10,1,38); 
SQL>select * from class; 
 
SQL> Select AVG(noofstudents) from class where teacherID IN(Select id from teacher 
Where subject=’science’ OR subject=’maths’); 
20.0 
SQL> SELECT * FROM student WHERE classID = (  SELECT id   FROM class   WHERE
2 noofstudents = (      SELECT MAX(noofstudents)      FROM class)); 
4|lucky |2|2.67 
5|ram   |2|4.56
