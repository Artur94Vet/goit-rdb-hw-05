## 2. Напишіть SQL запит, який буде відображати таблицю `order_details`. Відфільтруйте результати так, щоб відповідний запис із таблиці `orders` виконував умову shipper_id=3. Це має бути зроблено за допомогою вкладеного запиту в операторі WHERE. (Рисунок-2)

```sql
USE hw_03;
SELECT 
	od.*
FROM order_details AS od 
WHERE od.order_id IN (SELECT o.id FROM orders AS o WHERE o.shipper_id=3);
```
*Рисунок-2*  
<img width="1168" height="774" alt="image" src="https://github.com/user-attachments/assets/6e264b91-6933-40f4-9ac3-7e513fb2e6e3" />
