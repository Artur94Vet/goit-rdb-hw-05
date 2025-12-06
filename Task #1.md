## 1. Напишіть SQL запит, який буде відображати таблицю order_details та поле customer_id з таблиці orders відповідно для кожного поля запису з таблиці order_details. Це має бути зроблено за допомогою вкладеного запиту в операторі SELECT. (Рисунок-1)

```sql
USE hw_03;
SELECT 
	od.*
	,(SELECT o.customer_id FROM orders AS o WHERE od.order_id=o.id) AS customer_id 
FROM order_details AS od;
```
*Рисунок-1*  
<img width="812" height="798" alt="image" src="https://github.com/user-attachments/assets/9c21f7b9-db00-40fb-84d3-5f813c54309a" />

