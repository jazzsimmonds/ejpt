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
    
    ```Queries
    > SHOW databases;
    > SHOW tables FROM databases;
    > USE database;
    > SELECT * FROM table;
    
    Get password hash:
    > select load_file("/etc/shadow");
    > load_file("/etc/shadow");
    ```
</details>
<details>
<summary>Metaploit</summary>
    
    ```
    auxiliary/scanner/mysql/mysql_schemadump
    auxiliary/scanner/mysql/mysql_writable_dirs
    auxiliary/scanner/mysql/mysql_file_enum
    auxiliary/scanner/mysql/mysql_hashdump
    ```
</details>

<details>
<summary>nmap</summary>
    
    ```scripts
    --script=mysql-empty-password ~ check for anonymous login
    ```
</details>
<aside>
💡 For Finding all important files in Windows:(CTF Style)

`cd c:\Users` then
`tree /F`

</aside>

## Vulnerability Assessment
