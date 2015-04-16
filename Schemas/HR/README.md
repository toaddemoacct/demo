Ora11HRdb
=========

Oracle 11 db hr database


* Download XE 11 database -- http://www.oracle.com/technetwork/database/database-technologies/express-edition/overview/index.html
* Learn to Use Oracle Database 11g Express Edition - Part 1  -- https://apex.oracle.com/pls/otn/f?p=44785:24:101998711145653:::24:P24_CONTENT_ID,P24_PROD_SECTION_GRP_ID,P24_PREV_PAGE:5813,,24
* Other docs - http://docs.oracle.com/cd/E17781_01/index.htm
* about xe 11g -- http://docs.oracle.com/cd/E17781_01/admin.112/e18585/toc.htm
 

##Installing the HR Schema

All scripts necessary to create the Human Resource (HR) schema reside in $ORACLE_HOME/demo/schema/human_resources.

You need to call only one script, hr_main.sql, to create all the objects and load the data. The following steps provide a summary of the installation process:

    Log on to SQL*Plus as SYS and connect using the AS SYSDBA privilege.


    sqlplus connect sys as sysdba
    Enter password: password


    To run the hr_main.sql script, use the following command:


    SQL> @?/demo/schema/human_resources/hr_main.sql

    Enter a secure password for HR

    specify password for HR as parameter 1:
    Enter value for 1:
    
    

    Enter a secure password for HR

    specify password for HR as parameter 1:
    Enter value for 1:

    See Also:
    Oracle Database Security Guide for the minimum password requirements

    Enter an appropriate tablespace, for example, users as the default tablespace for HR

    specify default tablespace for HR as parameter 2:
    Enter value for 2:

    Enter temp as the temporary tablespace for HR

    specify temporary tablespace for HR as parameter 3:
    Enter value for 3:

    Enter your SYS password

    specify password for SYS as parameter 4:
    Enter value for 4:

    Enter the directory path, for example, $ORACLE_HOME/demo/schema/log/, for your log directory

    specify log path as parameter 5:
    Enter value for 5:

After the hr_main.sql script runs successfully and the HR schema is installed, you are connected as the user HR. To verify that the schema was created, use the following command:

SQL> SELECT       table_name FROM user_tables;

Running hr_main.sql accomplishes the following tasks:

    Removes any previously installed HR schema

    Creates the user HR and grants the necessary privileges

    Connects as HR

    Calls the scripts that create and populate the schema objects

For a complete listing of the scripts and their functions, refer to Table 5-1.

A pair of optional scripts, hr_dn_c.sql and hr_dn_d.sql, is provided as a schema extension. To prepare the HR schema for use with the directory capabilities of Oracle Internet Directory, run the hr_dn_c.sql script. If you want to return to the initial setup of the HR schema, then use the hr_dn_d.sql script to undo the effects of the hr_dn_c.sql script.

Use the hr_drop.sql script to drop the HR schema.
