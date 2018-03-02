# Notes-dbms-
Cardinality of Relation

No. of rows is cardinality of relation(5 rows --5 cardinality)
degree of relation---columns number
relation,entity ,table --same
attributes--columns
rows--Tuple,record

 **Degree of Relationship -- number of entities involved
 **Cardinality of Relationship -- no. of entity entering into relationship-- 1-to-1 ,1-to-many ,many-to-many 
 **when cardinality is 1-to-1 : you can have foreign key either side
 ---Example -- Trainees to Assessments , Degree-2, Cardinality is many-to-many
																					
** if Cardinality of Relationship is many-to-many  then we have to make new table(3rd in above case)
_________________________________________________________________________________________________________________________________
TRUNCATE , DELETE-
*TRUNCATE REMOVES ROWS--TRUNCATE USES LESS TRANSACTION SPACE---DOESNOT MAINTAIN ANY LOG FILE(FASTER)
*DELETE--DML COMMAND-SLOWER THAN TRUNCATE--USES MORE TRANSACTION SPACE--ALLOWS ROLLBACK

ORDER BY DESC(DEFAULT INCREASING)
__________________________________________________________________________________________________________________________________________________________________
SELECT(FUNCTION NAME) FROM dual::
 
CHARACTER FUNCTION:
DUMMY TABLE (DOESNOT HAVE ANY VALUES,USED FOR ANY OPERATIONS,KEYWORD-DUEL)
UPPER
LOWER
SUBSTR(STRING,FIRST POSITION,NUMBER OF CHARACTERS)
LENGTH
***NUMBERIC FUNCTIONS--
ROUND,CEIL,FLOOR,ABS----ROUND(NUMBER,DECIMAL POINTS)---ROUND(200.57,1)---200.6
****DATE FUNCTIONS-----SYSDATE,SYSTIMESTAMP,MONTHS_BETWEEN,ADD_MONTHS(YYYY OR CCYY(CENTURY))

****CONVERSION FUNCTION----TO_CHAR(EXTRACT PART OF THE DATE),TO_DATE,TO_NUMBER:
FROM SYSDATE.TO_CHAR(SYSDATE,'DD-MM-YY') FROM dual
__________________________________________________________________________________________________________________________________________________________________
*******CONCAT:
SELECT CONCAT( ) FROM TABLE
SELECT city || country FROM TABLENAME(CONCAT)

*********REPLACING NULL VALUE WITH ANOTHER STRING
-SELECT NVL(COLUMN_NAME,'COLMN NOT AVAILABLE') AS COLUMN_NAME FROM TABLENAME
---IF COLUMN IS INTEGER THEN CHANGE DATA TYPE (TO_CHAR (COLUMN_NAME))

********IN PARENT TABLE WE CANNOT DELETE OR UPDATE ANY RECORD IF IT IS REFERRED BY CHILD TABLE**********
********IN CHILD TABLE WE CANNOT INSERT OR UPDATE IF IT DOESNOT EXIST IN PARENT ************************

----NUMBER(PRECISION,SCALE)--345--NUMBER(3,3)-0.345-----------------

****CONSTRAINTS CANNOT BE CREATED WHEN TABLE DATA IS IN VIOLATION*****

-----AGGREGATE FUNCTIONS(MULTIROW FUNCTIONS)---
SUM
MAX (CAN WORK ON STRING,ASCII)
MIN (SAME AS ABOVE)
AVG
COUNT-NUMBER OF ANY ATTRIBUTE(OCCURENCES)

*****DISCTINCT****(APPEAR AFTER SELECT CLAUSE,1 IN A QUERY,ONLY IN SELECT)
-----GROUP BY NEEDS AGGREGATION--------AGGREGATION WILL NEED GROUP BY AS SELECT HAS 2 COLUMNS------
--COLUMNS MENTIONED IN SELECT CLAUSE SHOULD BE USED IN GROUP BY CLAUSE--WE CAN INCLUDE OTHER COLUMNS OF TABLE IN GROUP BY--------

*****NESTED AGGREGATE FUNCTION THEN GROUP BY NECCESSARY********

-----AGGREGATE FUNCTION CANNOT APPEAR ON RHS OF EQUATION(SALARY==MAX(SALARY) IS WRONG)--SUBQUERY IS MANDATORY----
-----SUBQUERY CAN BE USED THROUGH SELECT,FROM,WHERE ,HAVING .---
____________________________________________________________________________________________________________________________________________________________________
*****************JOIN************
---TO JOIN TWO TABLES SHOULD HAVE COMMON COLUMNS----
----JOINING CONDITIONS(IF NUMBER OF TABLE IS N THEN WE NEED N-1 CONDITIONS)-------
---ON WITH JOIN -----' ,' WITH WHERE---FOR JOINS--
3 TABLES 2 CONDITIONS;
FROM TABLE1 JOIN TABLE2 ON CONDITION;
FROM TABLE1,TABLE2 WHERE CONDITION;
____________________________________________________________________________________________________________________________________________________________________
---------INSERT ALL---INSERT ALL STATEMENTS---
INSERT ALL 
	INTO ()
	INTO ()
FROM DUAL;

WHERE --SINGLE ROW COLUMN -IF AGGREGATION FUNCTION IS ON RHS
HAVING----MULTI ROW COLUMN,IF AGGREGATE FUNCTION IS ON LHS--

--TABLE AFTER FROM IS MAIN TABLE , TABLE ON RIGHT SIDE IS LOOKUP TABLE--
--ADDITIONAL FILTER CONDITION USING A COLUMN AND THE COLUMN IS FROM LOOKUP USE 'AND' CLAUSE----(ONLY IN OUTER JOIN)

**SELF JOIN**(
FROM EMP E JOIN EMP A 
ON E.JOB=A.JOB)*****

******CORRELATED SUBQUERY(NESTED FOR LOOP)*******(CAN BE SOLVED BY SELFJOIN)
******INEPENDENT SUBQUERY*********

----CASE
WHEN DEPARTMENT='ETA' OR DEPARTMENT='SE' THEN TO_CHAR(SALARY*1.1)
ELSE ----
-----
---WHEN AND THEN----IF-ELSE---

_________________________________________________________________________________________________________________________________________________________________
SCENARIOS----
**WHEN 2 TABLES DONT HAVE ANY COLUMN COMMON WE USE 3RD TABLE WHICH HAVE COMMON COLUMN WITH USING TWO OUTER JOINS*****
********CORRELATED SUBQUERIES CAN BE REPLACED BY SELFJOINS******

UNIONS -----
SELECT STATEMENT --THEN UNION KEYWORD
SELECT STATEMENT___
UNION COMBINES TWO TABLES REMOVES DUPLICATE TUPLES-------------





__________________________________________________________________________________________________________________________________________________________________
