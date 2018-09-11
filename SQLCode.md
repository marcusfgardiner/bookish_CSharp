CREATE TABLE Users
(UserID int IDENTITY(1,1) primary key,
FirstName nvarchar(40),
LastName nvarchar(40),
UserName nvarchar(40),
Password nvarchar(40),
Email nvarchar(40),
Created datetime)

CREATE TABLE Books
(BookID int IDENTITY(1,1) primary key,
Title nvarchar(40),
ISBN nvarchar(13),
Author nvarchar(40),
Barcode nvarchar(40),
Created datetime)

CREATE TABLE UserBooks
(BorrowedID int IDENTITY(1,1) primary key,
UserID int foreign key references Users(UserID),
BookID int foreign key references Books(BookID),
RentalDate datetime,
DueDate datetime,
ReturnedDate datetime)