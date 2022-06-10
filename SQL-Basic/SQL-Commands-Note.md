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