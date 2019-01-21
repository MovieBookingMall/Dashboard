Dataset of TicketPlus
=====================

1 ER模型
--------

![](
https://github.com/MovieBookingMall/Dashboard/blob/master/images/02-01-1.jpg?raw=true)

2 关系模型
----------

-   用户 : 购票 = 1 : N

>   用户（*\*\*用户ID\*\**, 用户NAME，密码PASSWORD，性别SEX，地址ADDR，年龄AGE）

>   电影票（*\*\*电影票ID\*\**，座位号SEATS，单价PRICE，时间TIME，厅号ROOM，备注REMARK）

>   购票 ( *\*\*用户ID\*\**，\*\*电影票ID\*\*，总价TOTALPRICE，数量AMOUNTS)

-   主键: 用户ID

-   外键: 电影票ID

-   用户 : 电影 = N : Ｍ

>   用户（*\*\*用户ID\*\**, 用户NAME）

>   电影（*\*\*电影ID\*\**,
>   电影NAME，单价PRICE，标签TAGS，介绍INTRO，时长DURATION，制作商PRODUCER，导演DIRECTOR，地区REGION，演员ACTORS）

>   选择（*\*\*用户ID\*\**，*\*\*电影ID\*\**）

-   复合主键: 用户ID，电影ID

-   外键: 用户ID，电影ID

-   电影院 : 电影票 = 1 : N

>   电影院（*\*\*电影院ID\*\**，电影院NAME，省份PROVINCE，城市CITY，特点FEATURE）

>   电影票（*\*\*电影票ID\*\**，座位号SEATS，单价PRICE，播放时间TIME，厅号ROOM，备注REMARK）

>   管理１（*\*\*电影院ID\*\**，\*\*电影票ID\*\*）

-   主键: 电影院ID

-   外键: 电影票ID

-   电影院 : 电影 = 1 : N

>   电影院（*\*\*电影院ID\*\**，电影院NAME，省份PROVINCE，城市CITY，特点FEATURE）

>   电影（*\*\*电影ID\*\**,
>   电影NAME，单价PRICE，标签TAGS，介绍INTRO，时长DURATION，制作商PRODUCER，导演DIRECTOR，地区REGION，演员ACTORS）

>   管理２（*\*\*电影院ID\*\**，\*\*电影ID\*\*）

-   主键: 电影院ID

-   外键: 电影ID

3 数据库物理模型
----------------

-   **User**

| **Field** | **Type**     | **Key** | **Description**      |
|-----------|--------------|---------|----------------------|
| usr_id    | int          | PRI     | The ID of user       |
| account   | varchar(20)  |         | The account of user  |
| pwd       | varchar(24)  |         | The password of user |
| name      | varchar(20)  |         | The name of user     |
| age       | int          |         | The age of user      |
| addr      | varchar(100) |         | The address of user  |
| sex       | varchar(2)   |         | The sex of user      |

-   **Movie**

| **Field**    | **Type**     | **Key** | **Description**           |
|--------------|--------------|---------|---------------------------|
| movie_id     | int          | PRI     | The movie_id of movie     |
| name         | varchar(20)  |         | The name of movie         |
| price        | float        |         | The price of movie        |
| tag          | varchar(40)  |         | The tag of movie          |
| introduction | varchar(200) |         | The introduction of movie |
| duration     | varchar(11)  |         | The duration of movie     |
| producer     | varchar(20)  |         | The sex of movie          |
| director     | varchar(50)  |         | The director of movie     |
| region       | varchar(20)  |         | The region of movie       |
| actors       | varchar(50)  |         | The actors of movie       |

-   **Cinemal**

| **Field**  | **Type**    | **Key** | **Description**           |
|------------|-------------|---------|---------------------------|
| cinemal_id | int         | PRI     | The cinemal_id of cinemal |
| name       | varchar(20) |         | The name of cinemal       |
| province   | varchar(20) |         | The province of cinemal   |
| city       | varchar(20) |         | The city of cinemal       |
| feature    | varchar(20) |         | The feature of cinemal    |

-   **Tickets**

| **Field**   | **Type**    | **Key** | **Description**            |
|-------------|-------------|---------|----------------------------|
| ticket_id   | int         | PRI     | The ticket_id of tickets   |
| seat_number | int         |         | The seat_number of tickets |
| room        | int         |         | The room of tickets        |
| time        | date & time |         | The time of tickets        |
| price       | float       |         | The price of tickets       |
| remark      | varchar(50) |         | The remark of tickets      |

-   **Ordering**

| **Field**   | **Type** | **Key** | **Description**            |
|-------------|----------|---------|----------------------------|
| usr_id      | int      | PRI     | The usr_id of user         |
| ticket_id   | int      |         | The ticket_id of tickets   |
| total_price | float    |         | The total_price of tickets |
| amounts     | int      |         | The amounts of tickets     |

-   **Select**

| **Field** | **Type** | **Key** | **Description**         |
|-----------|----------|---------|-------------------------|
| usr_id    | int      | PRI     | The usr_id of user      |
| movie_id  | int      | PRI     | The ticket_id of ticket |

-   **Manager1**

| **Field**  | **Type** | **Key** | **Description**           |
|------------|----------|---------|---------------------------|
| cinemal_id | int      | PRI     | The cinemal_id of cinemal |
| ticket_id  | int      |         | The ticket_id of ticket   |

-   **Manager2**

| **Field**  | **Type** | **Key** | **Description**           |
|------------|----------|---------|---------------------------|
| cinemal_id | int      | PRI     | The cinemal_id of cinemal |
| movie_id   | int      |         | The ticket_id of ticket   |
