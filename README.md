

# MySQL

[CentOS下安装MySQL](https://dev.mysql.com/doc/refman/5.6/en/linux-installation-yum-repo.html)

create database better_me character set=utf8;

use mysql;

create table app_user(
   user_id int(11) not null auto_increment primary key,
   user_name varchar(50) not null,
   password varchar(50) not null,
   register_time timestamp not null default current_timestamp()
)CHARACTER SET=utf8 ENGINE=InnoDB;

create table event_record(
   user_id int(11) not null,
   item_name varchar(200) not null,
   point int(20) not null,
   remark varchar(200) null,
   create_time timestamp not null default current_timestamp(),
   foreign key(user_id) references app_user(user_id) on delete cascade
)CHARACTER SET=utf8 ENGINE=InnoDB;
