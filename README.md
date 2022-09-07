CREATE TABLE Product (
Id INT PRIMARY KEY,
"Name" TEXT
);

INSERT INTO Product
VALUES
(1, 'Pork'),
(2, 'Potato'),
(3, 'Milk');

CREATE TABLE Category (
Id INT PRIMARY KEY,
"Name" TEXT
);

INSERT INTO Category
VALUES
(1, 'Meet'),
(2, 'Vegetables'),
(3, 'Dairy_produce');

CREATE TABLE ProductCategory (
ProductId INT FOREIGN KEY REFERENCES Product(Id),
CategoryId INT FOREIGN KEY REFERENCES Category(Id),
PRIMARY KEY (ProductId, CategoryId)
);

INSERT INTO ProductCategories
VALUES
(1, 1),
(2, 2),
(3, 3);

SELECT P."Name", C."Name"
FROM Product AS P
LEFT JOIN ProductCategory AS PC
ON P.Id = PC.ProductId
LEFT JOIN Categories C
ON PC.CategoryId = C.Id;
