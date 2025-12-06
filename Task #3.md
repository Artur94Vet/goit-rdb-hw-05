## 3. Напишіть SQL запит, вкладений в операторі `FROM`, який буде обирати рядки з умовою `quantity>10` з таблиці `order_details`. Для отриманих даних знайдіть середнє значення поля `quantity` — групувати слід за `order_id`. (Рисунок-3)

```sql
USE hw_03;
SELECT
	od.order_id 
	,AVG(od.quantity) AS avg_quantity 
FROM (SELECT order_id,quantity FROM order_details WHERE quantity>10) AS od 
GROUP BY 
	od.order_id; 
```
*Рисунок-3*  
<img width="1219" height="784" alt="image" src="https://github.com/user-attachments/assets/ac18daf1-d29b-4100-bc35-39f4eca5563c" />
