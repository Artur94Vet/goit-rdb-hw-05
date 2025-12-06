## 4. Розв’яжіть завдання 3, використовуючи оператор WITH для створення тимчасової таблиці temp. Якщо ваша версія MySQL більш рання, ніж 8.0, створіть цей запит за аналогією до того, як це зроблено в конспекті. (Рисунок-4)

```sql
USE hw_03;
WITH
	temp AS (SELECT order_id,quantity FROM order_details WHERE quantity>10)

SELECT
	od.order_id 
	,AVG(od.quantity) AS avg_quantity 
FROM temp AS od 
GROUP BY 
	od.order_id;
```
*Рисунок-4*  
<img width="851" height="827" alt="image" src="https://github.com/user-attachments/assets/cc9b2d37-e9f9-495a-b6ea-7fcbe545efca" />
