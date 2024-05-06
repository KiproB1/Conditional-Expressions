# Conditional-Expressions
CREATE DATABASE MyCompany;

USE MyCompany;

CREATE TABLE Employees (
  EmployeeID INT PRIMARY KEY,
  FirstName VARCHAR(255) NOT NULL,
  LastName VARCHAR(255) NOT NULL,
  Salary DECIMAL(10,2) NOT NULL,
  BonusPercentage DECIMAL(2,1) NOT NULL
);
INSERT INTO Employees (FirstName, LastName, Salary, BonusPercentage)
VALUES ('John', 'Doe', 75000.00, 0.10),
       ('Jane', 'Smith', 62000.00, 0.05),
       ('Alice', 'Johnson', 90000.00, 0.15),
       ('Bob', 'Williams', 58000.00, 0.07),
       ('Charlie', 'Brown', 82000.00, 0.12);
ALTER TABLE Employees
ADD COLUMN TotalCompensation DECIMAL(10,2) AS (Salary + (Salary * BonusPercentage));
SELECT *
FROM Employees
WHERE TotalCompensation > 80000;
UPDATE Employees
SET FirstName = 'LowCompensation'
WHERE TotalCompensation < 60000;
