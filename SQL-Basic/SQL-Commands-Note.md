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
 SELECT * FROM Customers 
 ORDER BY Country ASC, CustomerName DESC;

 Xóa khách hàng có tên 'Alfreds Futterkiste' ra khỏi bảng khách hàng trong CSDL :
DELETE FROM Customers 
WHERE CustomerName = 'Alfreds Futterkiste';

Thêm 1 khác hàng mới vào bảng với thông tin như sau: 
CustomerName = 'Cardinal', 
ContactName = 'Tom B. Erichsen'
Address = 'Skagen 21'
City = 'Stavanger'
PostalCode = '4006'
Country = 'Norway' : INSERT INTO Customers 
(CustomerName,ContactName,Address,City,PostalCode,Country) 
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');

Cập nhật toàn bộ tên liên lạc = 'Juan' cho những khách hàng ở Mexico :
UPDATE Customers SET 
ContactName = 'Juan' WHERE Country = 'Mexico';

Đếm số lượng sản phẩm có trong bảng :
SELECT COUNT (ProductName) FROM Products;

Đếm số lượng sản phẩm có giá nhỏ hơn 40 :
SELECT COUNT (ProductName)
 FROM Products WHERE Price < 40;

 Lấy trung bình giá của sản phẩm :
 SELECT AVG (Price) FROM Products;

 Cho biết giá sản phẩm cao nhất, giá sản phẩm thấp nhất :
 SELECT MIN (Price), MAX (Price) FROM Products;

 Lọc ra những sản phẩm có giá từ 40 đến 90 ( lấy những sản phẩm có giá = 40 và = 90) :
 SELECT * FROM Products WHERE Price >= 40 AND Price <= 90;

 Lấy ra sản phẩm mà chưa từng được order :
 SELECT Products.ProductName, Products.ProductID FROM Products 
 JOIN OrderDetails ON Products. ProductID = OrderDetails.ProductID
  WHERE Products. ProductID <> OrderDetails.ProductID;

  Lọc ra danh sách tên khách hàng, tên liên lạc của khách hàng và lưu vào 1 bảng mới :
  CREATE TABLE NEWTABLE AS
  SELECT CustomerName, ContactName
   FROM CUSTOMERS;

   Lọc ra những khách hàng có quốc tịch Đức để lưu vào 1 bảng mới :
   CREATE TABLE NEWTABLE2 AS
    SELECT Country='Germany'
    FROM Customers;

    Lấy ra những quốc gia có trên 5 khách hàng và sắp xếp danh sách theo số lượng khách hàng giảm dần :
    SELECT COUNT(CustomerID), Country
    FROM Customers
   GROUP BY Country
   HAVING COUNT(CustomerID) > 5
   ORDER BY COUNT(CustomerID) DESC;

   Lấy ra tên sản phẩm có giá cao nhất trong bảng :
   SELECT MAX(Price) AS MaxPrice, ProductName FROM Products ORDER BY ProductName;

   Lọc ra những sản phẩm thuộc nhà cung cấp 'Exotic Liquid' :SELECT * FROM Products 
   JOIN Suppliers ON Products.SupplierID = Suppliers.SupplierID 
   WHERE Suppliers.SupplierName = 'Exotic Liquid';

   Lấy ra danh sách city ở khách hàng và nhà cung cấp rồi sắp xếp theo thứ tự tăng dần :
   SELECT Customers.City, Suppliers.City FROM Customers, 
   Suppliers ORDER BY Customers.City, Suppliers.City DESC;

Đếm số lượng sản phẩm của mỗi nhà cung cấp :
SELECT COUNT(ProductName), SupplierID
 FROM Products WHERE SupplierID IN (1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29) 
 GROUP BY SupplierID;

 Đếm số lượng sản phẩm được order theo productid và sắp xếp theo số lượng sản phẩm giảm dần :
 SELECT COUNT(ProductID) AS Total FROM [OrderDetails] GROUP BY ProductID ORDER BY Total DESC;

 Lấy ra những đơn hàng do shipper tên là 'United Package' ship mà có ngày order từ '01-01-1997':
 SELECT Orders.OrderID, Orders.OrderDate 
FROM Orders JOIN Shippers 
ON Orders.ShipperID = Shippers.ShipperID 
WHERE  ShipperName = 'United Package' 
GROUP BY Orders.OrderDate 
HAVING Orders.OrderDate > '1997-01-01';

Lấy ra danh sách tên nhà cung cấp mà có giá sản phẩm <20 :
SELECT Suppliers.SupplierName, Products.Price 
FROM Suppliers JOIN Products 
ON Suppliers.SupplierID=Products.SupplierID 
WHERE Products.Price <20;

Lấy ra danh sách tên nhà cung cấp mà có giá sản phẩm = 22 :
SELECT Suppliers.SupplierName, Products.Price 
FROM Suppliers JOIN Products 
ON Suppliers.SupplierID=Products.SupplierID 
WHERE Products.Price =22;

Lấy ra tên khách hàng và mã order tương ứng :
SELECT Customers.CustomerName, Orders.OrderID 
FROM Customers JOIN Orders 
ON Customers.CustomerID=Orders.CustomerID;

Lấy ra toàn bộ danh sách họ tên nhân viên và mã đơn hàng họ đặt được (nếu có) :
SELECT Employees.LastName, Employees.FirstName, Orders.OrderID 
FROM Employees JOIN Orders 
ON Employees.EmployeeID=Orders.EmployeeID;

Lấy ra id sản phẩm (productid) được order với số lượng nhiều nhất. 
Cho biết tên sản phẩm và số lượng sản phẩm đã được order nhiều nhất :
SELECT MAX(Quantity), OrderDetails.ProductID, Products.ProductName 
FROM OrderDetails JOIN Products 
ON OrderDetails.ProductID=Products.ProductID;

Lấy ra id khách hàng order trên 6 đơn :
SELECT Orders.CustomerID, OrderDetails. Quantity 
FROM OrderDetails JOIN Orders 
ON OrderDetails.OrderID=Orders.OrderID 
WHERE OrderDetails.Quantity > 6 
GROUP BY Orders.CustomerID;

Lấy ra những đơn hàng do shipper tên là 'United Package' ship mà có ngày order từ '01-01-1997' mà có tên khách hàng là 'Laura' :
FROM Orders 
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID 
INNER JOIN Customers ON Customers.CustomerID = Orders.CustomerID 
WHERE  ShipperName = 'United Package' 
GROUP BY Orders.OrderDate 
HAVING Orders.OrderDate > '1997-01-01';