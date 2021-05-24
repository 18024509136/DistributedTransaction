# DistributedTransaction
分布式事务学习  
DROP DATABASE IF  EXISTS  `bank1`;  
CREATE DATABASE `bank1` CHARACTER SET 'utf8mb4';  
  
USE `bank1`;  
  
DROP TABLE IF EXISTS `account_info`;  
CREATE TABLE `account_info` (  
		id bigint ( 20 ) NOT NULL  AUTO_INCREMENT COMMENT '主键',  
		account_name VARCHAR ( 100 ) COMMENT '账户姓名',  
		account_no VARCHAR ( 100 ) COMMENT '账户卡号',  
		account_password VARCHAR ( 100 ) COMMENT '账户密码',  
		account_balance DECIMAL ( 10,2) COMMENT '账户余额',  
		PRIMARY KEY ( id )   
) COMMENT = '账户表';  
  
INSERT INTO `account_info` VALUES ('1' , '张三的账户','1', '', 10000 );  
  
DROP DATABASE IF  EXISTS  `bank2`;  
CREATE DATABASE `bank2` CHARACTER SET 'utf8mb4';  
USE `bank2`;

DROP TABLE IF EXISTS `account_info`;  
CREATE TABLE `account_info` (  
		id bigint ( 20 ) NOT NULL  AUTO_INCREMENT COMMENT '主键',  
		account_name VARCHAR ( 100 ) COMMENT '账户姓名',  
		account_no VARCHAR ( 100 ) COMMENT '账户卡号',  
		account_password VARCHAR ( 100 ) COMMENT '账户密码',  
		account_balance DECIMAL ( 10,2)  COMMENT '账户余额',  
		PRIMARY KEY ( id )   
) COMMENT = '账户表';  
  
INSERT INTO `account_info` VALUES ('1' , '李四的账户','2', '', 0);  

每个数据库都建立  
CREATE TABLE `local_try_log` (  
`tx_no` varchar(64) not NUll comment '事务Id',  
`create_time` datetime DEFAULT NULL,  
PRIMARY KEY (`tx_no`)  
);  
  
CREATE TABLE `local_confirm_log` (  
`tx_no` varchar(64) not NUll comment '事务Id',  
`create_time` datetime DEFAULT NULL,  
PRIMARY KEY (`tx_no`)  
);  
  
CREATE TABLE `local_cancel_log` (  
`tx_no` varchar(64) not NUll comment '事务Id',  
`create_time` datetime DEFAULT NULL,  
PRIMARY KEY (`tx_no`)  
);  
  
https://blog.csdn.net/qq_39165426/article/details/106852111
