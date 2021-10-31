1.
SELECT Websites.name, Websites.url, access_log.count, access_log.date
FROM Websites, access_log
WHERE Websites.id=access_log.site_id and Websites.name="菜鸟教程";

从>=两个表中获取数据,WHERE ?=?是什么意思.
