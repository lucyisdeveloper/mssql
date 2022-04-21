# MSSQL 효율 향상😎
<br/>
<h4>☝️해당 문자열을 가지고 있는 프로시저 찾기</h4>
<p>
SELECT * <br/>
FROM sys.procedures p <br/>
INNER JON sys.syscomments s ON p.object_id = s.id <br/>
WHERE text LIKE '%[문자열]%'
</p>
<br/>
<h4>☝️해당 컬럼명을 가지고 있는 테이블 찾기</h4>
<p>
SELECT T.name AS table_name<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;, C.name AS column_name<br/>
FROM sys.tables AS T <br/>
INNER JOIN sys.columns AS C ON T.object_id = C.object_id<br/>
WHERE C.name = '컬럼명'
</p>
