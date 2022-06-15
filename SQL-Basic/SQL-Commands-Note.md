Source: https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all

Lấy ra toàn bộ thông tin trong bảng khách hàng: 
SELECT * 
FROM Customers;

Lấy ra toàn bộ tên các quốc gia trong bảng khách hàng: 
SELECT Country 
FROM Customers;

Lọc ra những khách hàng thuộc Canada: 
SELECT DISTINCT Country 'CANADA' 
FROM Customers;

Lọc ra những khách hàng có tên bắt đầu bằng kí tự "Bo": 
SELECT CustomerName 
FROM Customers 
WHERE CustomerName LIKE 'Bo%';

Lọc ra những khách hàng có tên chứa kí tự 'Bo' : 
Select CustomerName 
from Customers 
where CustomerName like '%Bo%';

Lấy ra tên khách hàng chưa đăng ký địa chỉ : 
SELECT * 
FROM Customers 
WHERE Address IS Null;

Lấy ra 3 khách hàng thuộc 'Germany' :
SELECT CustomerName 
FROM Customers 
where Country = 'Germany' LIMIT 3;

Lấy ra khách hàng thuộc 'Germany' hoặc 'Spain' : 
SELECT * FROM Customers 
where Country = 'Germany' or Country = 'Spain';

Lấy ra những khách hàng thuộc Germany hoặc France hoặc UK :
SELECT * FROM Customers
 where Country = 'Germany' or Country =  'France'or Country= 'UK';

Lấy ra những khách hàng thuộc Germany hoặc France hoặc UK :
SELECT * FROM Customers
 WHERE Country = 'Germany' OR Country = 'UK' OR Country = 'France' 
 ORDER BY Country;

 Sắp xếp khách hàng có Country tăng dần, tên khách hàng giảm dần theo thứ tự bảng chữ cái :
 SELECT * FROM Customers ORDER BY Country ASC, CustomerName DESC;