# SQLRequestManyToMany

Реализация запроса (многие ко многим). Таблицы: Products, Categories, ProductsCategories. С выбором всех продуктов (в том числе продукты без категории).

    SELECT product_name, Categories.category_name
    FROM Products
    LEFT JOIN ProductsCategories ON Product.Id = ProductsCategories.ProductId
    LEFT JOIN Categories on Categories.Id = ProductCategories.CategoriesId
