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

    Dump number of records in table:
    >SELECT count(*) FROM table;
    
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
        >  DIR_LIST /usr/share/metasploit-framework/data/wordlists/directory.txt
    auxiliary/scanner/mysql/mysql_file_enum
        > FILE_LIST /usr/share/metasploit-framework/data/wordlists/sensitive_files.txt
    auxiliary/scanner/mysql/mysql_hashdump
    ```
</details>

<details>
<summary>nmap</summary>
    
    ```scripts
    Check for anonymous login: --script=mysql-empty-password 
    Check if “InteractiveClient” capability is supported: --script=mysql-info
    Enumurate users: --script=mysql-users --script-args="mysqluser='root',mysqlpass=''"
    Enumurate DBs: --script=mysql-databases --script-args="mysqluser='root',mysqlpass=''" 
    Find Data Dir: --script=mysql-variables --script-args="mysqluser='root',mysqlpass=''" 
    Check if file privs can be granted for non-admin acc: p --script=mysql-audit --script-args="mysql-audit.username='root',mysql-audit.password='',mysql-audit.filename='/usr/share/nmap/n
selib/data/mysql-cis.audit'"
    Dump user hashs: --script mysql-dump-hashes --script-args="username='root',password=''"
    Find number of records stored in table: --script=mysql-query --script-args="query='select count(*) from
books.authors;',username='root',password=''"

    ```Example
     nmap --script=mysql-users --script-args="mysqluser='root',mysqlpass=''" -p 3306 192.71.145.3
    ```
</details>
<aside>
💡 For Finding all important files in Windows:(CTF Style)

`cd c:\Users` then
`tree /F`

</aside>

## Vulnerability Assessment
