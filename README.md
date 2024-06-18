# eJPT Cheatsheet

**exam prep**
# Table of Contents
https://github.com/jazzsimmonds/ejpt/blob/main/README.md#mysql

# Assessment Methodologies
## Information Gathering
## Footprinting and Scanning
## Enumuration
### MySQL
<details>
<summary>MySQL</summary>
    
    ```Connect
    mysql -h <ip address> -u <username>
    -p ~ password login
    ```Query
    > SHOW databases;
    > SHOW tables FROM databases;
    > USE database;
    > SELECT * FROM table;
    ```
</details>
<details>
<summary>Metaploit</summary>
    
    ```
    auxiliary/scanner/mysql/mysql_schemadump
    ```
</details>

<aside>
💡 For Finding all important files in Windows:(CTF Style)

`cd c:\Users` then
`tree /F`

</aside>

## Vulnerability Assessment
