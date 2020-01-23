# MYSQL

CREATE USER 'holberton_user'@'localhost' IDENTIFIED BY 'projectcorrection280hbtn';
GRANT ALL PRIVILEGES ON *.* TO 'holberton_user'@'localhost';

CREATE DATABASE tyrell_corp;
USE tyrell_corp;

CREATE TABLE IF NOT EXISTS nexus6 (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL
)  ENGINE=INNODB;

INSERT INTO nexus6 VALUES (1, 'Leon');

CREATE USER 'replica_user'@'%' IDENTIFIED BY 'projectcorrection280hbtn';
GRANT REPLICATION SLAVE ON *.* TO 'replica_user'@'%';

CHANGE MASTER TO MASTER_HOST='35.237.254.224',MASTER_PORT = 3306 ,MASTER_USER='replica_user', MASTER_PASSWORD='projectcorrection280hbtn', MASTER_LOG_FILE='mysql-bin.000013', MASTER_LOG_POS=154;
