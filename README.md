# Etiya-SQL-Queries

```sql
### Tedarikçi ID'si 1 ile 5 arasındaki ürünler:
SELECT * FROM Products WHERE SupplierID IN (1, 2, 3, 4, 5);

###  Tedarikçi ID'si 1, 2, 3, 4 veya 5 olan ürünleri listeleyin.

SELECT * from Suppliers where Suppliers.SupplierID in (1,2,4) OR Suppliers.SupplierID in (5)

### Tedarikçi ID'si 1, 2, 4 veya 5 olan ürünler:

SELECT * from Products WHERE Products.ProductName=='Chang' or Products.ProductName=='Aniseed Syrup'

### Ürün adı 'Chang' veya 'Aniseed Syrup' olan ürünler:

SELECT * from Products WHERE Products.ProductName=='Chang' or Products.ProductName=='Aniseed Syrup'

### Tedarikçi ID'si 3 olan veya birim fiyatı 10'dan büyük ürünler:

SELECT * FROM Products WHERE Products.SupplierID==3 or Products.UnitPrice>10

### Ürün adı ve birim fiyatı ile birlikte getirme:

SELECT Products.ProductName || ' ' || Products.UnitPrice FROM Products 

### Büyük harfe dönüştürerek 'c' harfi içeren ürünler:(örneğin: 'Chai', 'Chocolate', vs.)

SELECT CONCAT(
        UPPER(SUBSTRING(productname, 1, 1)),
        LOWER(SUBSTRING(productname, 2, LENGTH(productname)))
    ) AS capitalized_name FROM Products WHERE Products.ProductName LIKE '%c%'

### 'n' ile başlayan ve tek karakterli bir harf içeren ürünler:

SELECT * FROM Products WHERE Products.ProductName LIKE 'n_%'

### Stok miktarı 50'den fazla olan ürünler:

SELECT * FROM Products WHERE Products.UnitsInStock>50

### Ürünlerin en yüksek ve en düşük birim fiyatları:

SELECT *
FROM Products
WHERE Products.UnitPrice = (SELECT MAX(Products.UnitPrice) FROM Products)
UNION
SELECT *
FROM Products
WHERE Products.UnitPrice = (SELECT MIN(Products.UnitPrice) FROM Products)


### Ürün adında 'Spice' kelimesi geçen ürünler:

SELECT * FROM Products WHERE Products.ProductName LIKE '%Spice%'



 
 
 

 



