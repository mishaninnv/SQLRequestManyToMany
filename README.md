# SQLRequestManyToMany
Запрос выбирающий продукты и категории продуктов (отношение многие ко многим), выбираются все продукты даже те у которых нет категории.

SELECT dbo.Product.ProductName AS Product,
	(SELECT dbo.Category.CategoryName FROM dbo.Category
 	WHERE dbo.Category.CategoryId = dbo.ProductCategories.CategoryId) AS Category
FROM dbo.Product
LEFT OUTER JOIN dbo.ProductCategories on dbo.Product.ProductId = dbo.ProductCategories.ProductId 
