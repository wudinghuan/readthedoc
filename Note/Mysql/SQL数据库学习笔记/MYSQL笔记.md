1.起别名
以下两种写法相等
SELECT name, url AS site_info FROM websites;
SELECT name, url site_info FROM websites;
 
 
创建PROCEDURE
DROP PROCEDURE IF EXISTS add_student;
DELIMITER $$
CREATE PROCEDURE add_student(
	name VARCHAR(50),
    chinese TINYINT,
    math TINYINT,
    english TINYINT
)
BEGIN
	INSERT INTO `students`(name) VALUES(name);
    INSERT INTO `score`(student_id,Chinese,Math,English) VALUES(last_insert_id(),chinese,math,english);
END$$
DELIMITER ;


删除有外键的多个表时,比如A的主键是B的外键,先删除B在删除A



重新对主键排序
在对数据库进行操作的时候遇到了这样一个问题，数据库的表里的id是自增的，当数据被删除或者添加时，ID便会一直增上去，id就会变得很乱，不会按照顺序，今天查找了各个网站，终于找到了解决办法
alter table tablename drop column id;
alter table tablename add id mediumint(8) not null primary key auto_increment first;


表students的主键id是表score的外键,删除A的数据要添加触发器来同时删除B中的对应数据
DELIMITER $$
CREATE TRIGGER `delete_trigger` AFTER DELETE ON `students`
FOR EACH ROW 
begin
    DELETE  FROM score WHERE student_id = old.student_id;
end $$
DELIMITER ;
这里的old是删除students数据临时生成的表


查看存储过程procedure
select `name` from mysql.proc where db = 'xx' and `type` = 'FUNCTION' 
