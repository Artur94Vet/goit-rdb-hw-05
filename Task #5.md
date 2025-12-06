## 5. Створіть функцію з двома параметрами, яка буде ділити перший параметр на другий. Обидва параметри та значення, що повертається, повинні мати тип `FLOAT`. Використайте конструкцію `DROP FUNCTION IF EXISTS`. Застосуйте функцію до атрибута `quantity` таблиці `order_details` . Другим параметром може бути довільне число на ваш розсуд. (Рисунок-5)

```sql
USE hw_03;

DROP FUNCTION IF EXISTS f_divide;
DELIMITER //
CREATE FUNCTION f_divide 
(
    num1 FLOAT,
    num2 FLOAT
)
RETURNS FLOAT
NO SQL
DETERMINISTIC
BEGIN
    DECLARE result FLOAT;
    SET result = num1 / num2;
    RETURN result;
END;
//
DELIMITER ;

SET @div_x=2;

SELECT 
    quantity,
    f_divide(quantity, @div_x) AS divided_quantity
FROM order_details;
```
*Рисунок-5*  
<img width="772" height="847" alt="image" src="https://github.com/user-attachments/assets/2759a78b-bf8f-406e-a530-7973abfa08d6" />
