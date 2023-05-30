CREATE TABLE aggregate_table AS (
    SELECT
		CustomerID,
		OrderID,
        Date, 
        Full_Name,
		CustomerCity,
		CustomerState,
		ProdNumber,
		CategoryID,
		CategoryName,
		CategoryAbbreviation,
		ProdName,
		Category, 
        SUM(Quantity) AS TotalQuantity,
        SUM(Quantity*Price) AS TotalRevenue,
        SUM(Price) AS TotalPrice
    FROM
        master_table
    GROUP BY
		CustomerID,
		OrderID,
        Date, 
        Full_Name,
		CustomerCity,
		CustomerState,
		Quantity,
		ProdNumber,
        ProdName,
		Category, 
		Price,
		CategoryID,
		CategoryName,
		CategoryAbbreviation
);