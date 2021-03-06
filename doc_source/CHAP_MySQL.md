# MySQL on Amazon RDS<a name="CHAP_MySQL"></a>

Amazon RDS supports DB instances running several versions of MySQL\. You can use the following major versions: 
+ MySQL 5\.7
+ MySQL 5\.6
+ MySQL 5\.5

For more information about minor version support, see [MySQL on Amazon RDS Versions](#MySQL.Concepts.VersionMgmt)\. 

You first use the Amazon RDS management tools or interfaces to create an Amazon RDS MySQL DB instance\. You can then use the resizing the DB instance, authorizing connections to the DB instance, creating and restoring from backups or snapshots, creating Multi\-AZ secondaries, creating Read Replicas, and monitoring the performance of the DB instance\. You use standard MySQL utilities and applications to store and access the data in the DB instance\. 

Amazon RDS for MySQL is compliant with many industry standards\. For example, you can use Amazon RDS for MySQL databases to build HIPAA\-compliant applications and to store healthcare related information, including protected health information \(PHI\) under an executed Business Associate Agreement \(BAA\) with AWS\. Amazon RDS for MySQL also meets Federal Risk and Authorization Management Program \(FedRAMP\) security requirements and has received a FedRAMP Joint Authorization Board \(JAB\) Provisional Authority to Operate \(P\-ATO\) at the FedRAMP HIGH Baseline within the AWS GovCloud \(US\) region\. For more information on supported compliance standards, see [AWS Cloud Compliance](https://aws.amazon.com/compliance/)\. 

## Common Management Tasks for MySQL on Amazon RDS<a name="MySQL.Concepts.General"></a>

The following are the common management tasks you perform with an Amazon RDS MySQL DB instance, with links to relevant documentation for each task\. 


****  

| Task Area | Relevant Documentation | 
| --- | --- | 
|  **Understanding Amazon RDS** Understand key Amazon RDS components, including DB instances, regions, Availability Zones, security groups, parameter groups, and option groups\.  |  [What Is Amazon Relational Database Service \(Amazon RDS\)?](Welcome.md)  | 
|  **Setting up Amazon RDS for first time use** Set up Amazon RDS so that you can create MySQL DB instances in Amazon Web Services \(AWS\)\.  |  [Setting Up for Amazon RDS](CHAP_SettingUp.md)   | 
|  **Understanding Amazon RDS DB instances** Create virtual MySQL server instances that run in AWS\. Because DB instances are the building blocks of Amazon RDS, we recommend that you understand their principles\.  |  [Amazon RDS DB Instances](Overview.DBInstance.md)  | 
|  **Creating a DB instance for production** Create a DB instance for production purposes\. Creating an instance includes choosing a DB instance class with appropriate processing power and memory capacity and choosing a storage type that supports the way you expect to use your database\.   |   [DB Instance Class](Concepts.DBInstanceClass.md)   [Amazon RDS Storage Types](CHAP_Storage.md#Concepts.Storage)   [Creating a DB Instance Running the MySQL Database Engine](USER_CreateInstance.md)   | 
|  **Managing security for your DB instance** By default, DB instances are created with a firewall that prevents access to them\. You must create a security group with the correct IP addresses and network configuration to access the DB instance\. You can also use AWS Identity and Access Management \(IAM\) policies to assign permissions that determine who is allowed to manage RDS resources\.  |   [Security in Amazon RDS](UsingWithRDS.md)   [Overview of Managing Access Permissions to Your Amazon RDS Resources](UsingWithRDS.IAM.AccessControl.Overview.md)   [Amazon RDS Security Groups](Overview.RDSSecurityGroups.md)   [Determining Whether You Are Using the EC2\-VPC or EC2\-Classic Platform](USER_VPC.FindDefaultVPC.md)   | 
|  **Connecting to your DB instance** Connect to your DB instance using a standard SQL client application such as the MySQL command line utility or MySQL Workbench\.  |   [Connecting to a DB Instance Running the MySQL Database Engine](USER_ConnectToInstance.md)   | 
|  **Configuring high availability for a production DB instance ** Provide high availability with synchronous standby replication in a different Availability Zone, automatic failover, fault tolerance for DB instances using Multi\-AZ deployments, and Read Replicas\.  |   [High Availability \(Multi\-AZ\)](Concepts.MultiAZ.md)   | 
|  **Configuring a DB instance in an Amazon Virtual Private Cloud** Configure a virtual private cloud \(VPC\) in the Amazon VPC service\. An Amazon VPC is a virtual network logically isolated from other virtual networks in AWS\.   |   [Determining Whether You Are Using the EC2\-VPC or EC2\-Classic Platform](USER_VPC.FindDefaultVPC.md)   [Working with an Amazon RDS DB Instance in a VPC](USER_VPC.WorkingWithRDSInstanceinaVPC.md)   | 
|  **Configuring specific MySQL database parameters and features** Configure specific MySQL database parameters with a parameter group that can be associated with many DB instances\. You can also configure specific MySQL database features with an option group that can be associated with many DB instances\.  |   [Working with DB Parameter Groups](USER_WorkingWithParamGroups.md)   [Working with Option Groups](USER_WorkingWithOptionGroups.md)   [Options for MySQL DB Instances](Appendix.MySQL.Options.md)   | 
|  **Modifying a DB instance running the MySQL database engine** Change the settings of a DB instance to accomplish tasks such as adding additional storage or changing the DB instance class\.  |   [Modifying a DB Instance Running the MySQL Database Engine](USER_ModifyInstance.MySQL.md)   [Modifying an Amazon RDS DB Instance and Using the Apply Immediately Parameter](Overview.DBInstance.Modifying.md)   | 
|  **Configuring database backup and restore** Configure your DB instance to take automated backups\. You can also back up and restore your databases manually by using full backup files\.   |   [Working With Backups](USER_WorkingWithAutomatedBackups.md)   [Backing Up and Restoring Amazon RDS DB Instances](CHAP_CommonTasks.BackupRestore.md)   | 
|  **Importing and exporting data** Import data from other RDS MySQL DB instances, MySQL instances running external to Amazon RDS, and other types of data sources, and export data to MySQL instances running external to Amazon RDS\.  |   [Importing Data into an Amazon RDS MySQL DB Instance](MySQL.Procedural.Importing.md)   | 
|  **Monitoring a MySQL DB instance** Monitor your RDS MySQL DB instance by using Amazon CloudWatch RDS metrics, events, and Enhanced Monitoring\. View log files for your RDS MySQL DB instance\.  |   [Monitoring Amazon RDS](CHAP_Monitoring.md)   [Viewing DB Instance Metrics](CHAP_Monitoring.md#USER_Monitoring)   [Viewing Amazon RDS Events](USER_ListEvents.md)   [Amazon RDS Database Log Files](USER_LogAccess.md)   [MySQL Database Log Files](USER_LogAccess.Concepts.MySQL.md)   | 
|  **Replicating your data** Create a MySQL Read Replica—optionally, in a different AWS Region—for load balancing, disaster recovery, and processing read\-heavy database workloads, such as for analysis and reporting\.   |   [Working with Read Replicas of MariaDB, MySQL, and PostgreSQL DB Instances](USER_ReadRepl.md)   [Replication with a MySQL or MariaDB Instance Running External to Amazon RDS](MySQL.Procedural.Importing.External.Repl.md)   | 

There are also several appendices with useful information about working with Amazon RDS MySQL DB instances: 
+ [Common DBA Tasks for MySQL DB Instances](Appendix.MySQL.CommonDBATasks.md)
+ [Options for MySQL DB Instances](Appendix.MySQL.Options.md)
+ [Appendix: MySQL on Amazon RDS SQL Reference](Appendix.MySQL.SQLRef.md)

## MySQL on Amazon RDS Versions<a name="MySQL.Concepts.VersionMgmt"></a>

For MySQL, version numbers are organized as version = X\.Y\.Z\. In Amazon RDS terminology, X\.Y denotes the major version, and Z is the minor version number\. For Amazon RDS implementations, a version change is considered major if the major version number changes—for example, going from version 5\.6 to 5\.7\. A version change is considered minor if only the minor version number changes—for example, going from version 5\.7\.16 to 5\.7\.21\. 

Amazon RDS currently supports the following versions of MySQL: 


****  

| Major Version | Minor Version | 
| --- | --- | 
| MySQL 5\.7 |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html)  | 
| MySQL 5\.6 |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html)  | 
| MySQL 5\.5 |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html)  | 

You can specify any currently supported MySQL version when creating a new DB instance\. You can specify the MySQL 5\.7, 5\.6, or 5\.5 major versions, and any supported minor version for the specified major version\. If no version is specified, Amazon RDS will default to a supported version, typically the most recent version\. If a major version \(for example, MySQL 5\.7\) is specified but a minor version is not, Amazon RDS will default to a recent release of the major version you have specified\. To see a list of supported versions, as well as defaults for newly created DB instances, use the DescribeDBEngineVersions API action\.

With Amazon RDS, you control when to upgrade your MySQL instance to a new version supported by Amazon RDS\. You can maintain compatibility with specific MySQL versions, test new versions with your application before deploying in production, and perform version upgrades at times that best fit your schedule\.

Unless you specify otherwise, your DB instance will automatically be upgraded to new MySQL minor versions as they are supported by Amazon RDS\. This patching occurs during your scheduled maintenance window, and it is announced on the [ Amazon RDS Community Forum](https://forums.aws.amazon.com/) in advance\. To turn off automatic version upgrades, set the AutoMinorVersionUpgrade parameter to “false\.” 

 If you opt out of automatically scheduled upgrades, you can manually upgrade to a supported minor version release by following the same procedure as you would for a major version update\. For information, see [Upgrading the MySQL DB Engine](USER_UpgradeDBInstance.MySQL.md)\. 

Amazon RDS currently supports the major version upgrades from MySQL version 5\.5 to version 5\.6 and MySQL version 5\.6 to version 5\.7\. Because major version upgrades involve some compatibility risk, they do not occur automatically; you must make a request to modify the DB instance\. You should thoroughly test any upgrade before upgrading your production instances\. For information about upgrading a DB instance, see [Upgrading the MySQL DB Engine](USER_UpgradeDBInstance.MySQL.md)\. 

You can test a DB instance against a new version before upgrading by creating a DB snapshot of your existing DB instance, restoring from the DB snapshot to create a new DB instance, and then initiating a version upgrade for the new DB instance\. You can then experiment safely on the upgraded clone of your DB instance before deciding whether or not to upgrade your original DB instance\. 

For information about the Amazon RDS deprecation policy for MySQL, see [Amazon RDS FAQs](https://aws.amazon.com/rds/faqs/)\.

## MySQL Features Not Supported By Amazon RDS<a name="MySQL.Concepts.Features"></a>

Amazon RDS does not currently support the following MySQL features: 
+ Global Transaction IDs
+ Transportable Table Space
+ Authentication Plugin
+ Password Strength Plugin
+ Replication Filters
+ Semi\-synchronous Replication

 In order to deliver a managed service experience, Amazon RDS does not provide shell access to DB instances, and it restricts access to certain system procedures and tables that require advanced privileges\. Amazon RDS supports access to databases on a DB instance using any standard SQL client application\. Amazon RDS does not allow direct host access to a DB instance via Telnet, Secure Shell \(SSH\), or Windows Remote Desktop Connection\. When you create a DB instance, you are assigned to the *db\_owner* role for all databases on that instance, and you have all database\-level permissions except for those used for backups\. Amazon RDS manages backups for you\. 

## Supported Storage Engines for MySQL on Amazon RDS<a name="MySQL.Concepts.Storage"></a>

While MySQL supports multiple storage engines with varying capabilities, not all of them are optimized for recovery and data durability\. Amazon RDS fully supports the InnoDB storage engine for MySQL DB instances\. Amazon RDS features such as Point\-In\-Time restore and snapshot restore require a recoverable storage engine and are supported for the InnoDB storage engine only\. You must be running an instance of MySQL 5\.6 or later to use the InnoDB `memcached` interface\. For more information, see [MySQL `MEMCACHED` Support](Appendix.MySQL.Options.memcached.md)\. 

The Federated Storage Engine is currently not supported by Amazon RDS for MySQL\. 

The MyISAM storage engine does not support reliable recovery and can result in lost or corrupt data when MySQL is restarted after a recovery, preventing Point\-In\-Time restore or snapshot restore from working as intended\. However, if you still choose to use MyISAM with Amazon RDS, snapshots can be helpful under some conditions\. 

If you want to convert existing MyISAM tables to InnoDB tables, you can use the alter table command \(for example, alter table TABLE\_NAME engine=innodb;\)\. Bear in mind that MyISAM and InnoDB have different strengths and weaknesses, so you should fully evaluate the impact of making this switch on your applications before doing so\. 

MySQL 5\.1 is no longer supported in Amazon RDS\. However, you can restore existing MySQL 5\.1 snapshots\. When you restore a MySQL 5\.1 snapshot, the instance is automatically upgraded to MySQL 5\.5\. 

## MySQL Security on Amazon RDS<a name="MySQL.Concepts.UsersAndPrivileges"></a>

Security for Amazon RDS MySQL DB instances is managed at three levels:
+ AWS Identity and Access Management controls who can perform Amazon RDS management actions on DB instances\. When you connect to AWS using IAM credentials, your IAM account must have IAM policies that grant the permissions required to perform Amazon RDS management operations\. For more information, see [Authentication and Access Control for Amazon RDS](UsingWithRDS.IAM.md)\. 
+ When you create a DB instance, you use either a VPC security group or a DB security group to control which devices and Amazon EC2 instances can open connections to the endpoint and port of the DB instance\. These connections can be made using SSL\. In addition, firewall rules at your company can control whether devices running at your company can open connections to the DB instance\. 
+ To authenticate login and permissions for a MySQL DB instance, you can take either of the following approaches, or a combination of them\. 

  You can take the same approach as with a stand\-alone instance of MySQL\. Commands such as `CREATE USER`, `RENAME USER`, `GRANT`, `REVOKE`, and `SET PASSWORD` work just as they do in on\-premises databases, as does directly modifying database schema tables\. For information, see [MySQL User Account Management](https://dev.mysql.com/doc/mysql-security-excerpt/5.6/en/user-account-management.html) in the MySQL documentation\. 

  You can also use IAM database authentication\. With IAM database authentication, you authenticate to your DB instance by using an IAM user or IAM role and an authentication token\. An *authentication token* is a unique value that is generated using the Signature Version 4 signing process\. By using IAM database authentication, you can use the same credentials to control access to your AWS resources and your databases\. For more information, see [IAM Database Authentication for MySQL and Amazon Aurora](UsingWithRDS.IAMDBAuth.md)\. 

 When you create an Amazon RDS DB instance, the master user has the following default privileges: 
+ `alter`
+ `alter routine`
+ `create`
+ `create routine`
+ `create temporary tables`
+ `create user`
+ `create view`
+ `delete`
+ `drop`
+ `event`
+ `execute`
+ `grant option`
+ `index`
+ `insert`
+ `lock tables`
+ `process`
+ `references`
+ `replication client`
+ `replication slave (MySQL 5.6 and later) `
+ `select`
+ `show databases`
+ `show view`
+ `trigger`
+ `update`

**Note**  
Although it is possible to delete the master user on the DB instance, it is not recommended\. To recreate the master user, use the [ModifyDBInstance](http://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_ModifyDBInstance.html) RDS API action or the [modify\-db\-instance](http://docs.aws.amazon.com/cli/latest/reference/rds/modify-db-instance.html) AWS CLI command and specify a new master user password with the appropriate parameter\. If the master user does not exist in the instance, the master user is created with the specified password\. 

To provide management services for each DB instance, the `rdsadmin` user is created when the DB instance is created\. Attempting to drop, rename, change the password, or change privileges for the `rdsadmin` account will result in an error\. 

To allow management of the DB instance, the standard `kill` and `kill_query` commands have been restricted\. The Amazon RDS commands `rds_kill` and `rds_kill_query` are provided to allow you to terminate user sessions or queries on DB instances\. 

## Using SSL with a MySQL DB Instance<a name="MySQL.Concepts.SSLSupport"></a>

Amazon RDS supports SSL connections with DB instances running the MySQL database engine\. 

**Note**  
Amazon Aurora is compatible with MySQL\. However, you use a different SSL certificate to connect to an Amazon Aurora DB cluster\. For information on connecting to Amazon Aurora using SSL, see [Using SSL with Aurora DB Clusters](Aurora.Overview.md#Aurora.Overview.Security.SSL)\. 

Amazon RDS creates an SSL certificate and installs the certificate on the DB instance when Amazon RDS provisions the instance\. These certificates are signed by a certificate authority\. The SSL certificate includes the DB instance endpoint as the Common Name \(CN\) for the SSL certificate to guard against spoofing attacks\. The public key is stored at [https://s3\.amazonaws\.com/rds\-downloads/rds\-combined\-ca\-bundle\.pem](https://s3.amazonaws.com/rds-downloads/rds-combined-ca-bundle.pem)\. 

An SSL certificate created by Amazon RDS is the trusted root entity and should work in most cases but might fail if your application does not accept certificate chains\. If your application does not accept certificate chains, you might need to use an intermediate certificate to connect to your region\. For example, you must use an intermediate certificate to connect to the AWS GovCloud \(US\) region using SSL\. For a list of regional intermediate certificates that you can download, see [Intermediate Certificates](UsingWithRDS.SSL.md#UsingWithRDS.SSL.IntermediateCertificates)\. 

MySQL uses yaSSL for secure connections in the following versions:
+ MySQL version 5\.7\.19 and earlier
+ MySQL version 5\.6\.37 and earlier
+ MySQL version 5\.5\.57 and earlier

MySQL uses OpenSSL for secure connections in the following versions:
+ MySQL version 5\.7\.21 and later
+ MySQL version 5\.6\.39 and later
+ MySQL version 5\.5\.59 and later

To encrypt connections using the default `mysql` client, launch the mysql client using the `--ssl-ca parameter` to reference the public key, for example: 

For MySQL 5\.7 and later:

```
mysql -h myinstance.c9akciq32.rds-us-east-1.amazonaws.com
--ssl-ca=[full path]rds-combined-ca-bundle.pem --ssl-mode=VERIFY_IDENTITY
```

For MySQL 5\.6 and earlier:

```
mysql -h myinstance.c9akciq32.rds-us-east-1.amazonaws.com
--ssl-ca=[full path]rds-combined-ca-bundle.pem --ssl-verify-server-cert
```

You can require SSL connections for specific users accounts\. For example, you can use one of the following statements, depending on your MySQL version, to require SSL connections on the user account `encrypted_user`\.

For MySQL 5\.7 and later:

```
ALTER USER 'encrypted_user'@'%' REQUIRE SSL;            
```

For MySQL 5\.6 and earlier:

```
GRANT USAGE ON *.* TO 'encrypted_user'@'%' REQUIRE SSL;            
```

For more information on SSL connections with MySQL, go to the [MySQL documentation](https://dev.mysql.com/doc/refman/5.6/en/secure-connections.html)\. 

## Using memcached and Other Options with MySQL<a name="MySQL.Concepts.General.Options"></a>

Most Amazon RDS DB engines support option groups that allow you to select additional features for your DB instance\. DB instances on MySQL version 5\.6 and later support the `memcached` option, a simple, key\-based cache\. For more information about `memcached` and other options, see [Options for MySQL DB Instances](Appendix.MySQL.Options.md)\. For more information about working with option groups, see [Working with Option Groups](USER_WorkingWithOptionGroups.md)\. 

## InnoDB Cache Warming<a name="MySQL.Concepts.InnoDBCacheWarming"></a>

InnoDB cache warming can provide performance gains for your MySQL DB instance by saving the current state of the buffer pool when the DB instance is shut down, and then reloading the buffer pool from the saved information when the DB instance starts up\. This bypasses the need for the buffer pool to "warm up" from normal database use and instead preloads the buffer pool with the pages for known common queries\. The file that stores the saved buffer pool information only stores metadata for the pages that are in the buffer pool, and not the pages themselves\. As a result, the file does not require much storage space\. The file size is about 0\.2 percent of the cache size\. For example, for a 64 GB cache, the cache warming file size is 128 MB\. For more information on InnoDB cache warming, go to [Saving and Restoring the Buffer Pool State](https://dev.mysql.com/doc/refman/5.6/en/innodb-preload-buffer-pool.html) in the MySQL documentation\. 

MySQL on Amazon RDS supports InnoDB cache warming for MySQL version 5\.6 and later\. To enable InnoDB cache warming, set the `innodb_buffer_pool_dump_at_shutdown` and `innodb_buffer_pool_load_at_startup` parameters to 1 in the parameter group for your DB instance\. Changing these parameter values in a parameter group will affect all MySQL DB instances that use that parameter group\. To enable InnoDB cache warming for specific MySQL DB instances, you might need to create a new parameter group for those instances\. For information on parameter groups, see [Working with DB Parameter Groups](USER_WorkingWithParamGroups.md)\. 

InnoDB cache warming primarily provides a performance benefit for DB instances that use standard storage\. If you use PIOPS storage, you do not commonly see a significant performance benefit\. 

**Important**  
If your MySQL DB instance does not shut down normally, such as during a failover, then the buffer pool state will not be saved to disk\. In this case, MySQL loads whatever buffer pool file is available when the DB instance is restarted\. No harm is done, but the restored buffer pool might not reflect the most recent state of the buffer pool prior to the restart\. To ensure that you have a recent state of the buffer pool available to warm the InnoDB cache on startup, we recommend that you periodically dump the buffer pool "on demand\." You can dump or load the buffer pool on demand if your DB instance is running MySQL version 5\.6\.19 or later\.  
You can create an event to dump the buffer pool automatically and on a regular interval\. For example, the following statement creates an event named `periodic_buffer_pool_dump` that dumps the buffer pool every hour\.   

```
1. CREATE EVENT periodic_buffer_pool_dump 
2. ON SCHEDULE EVERY 1 HOUR 
3. DO CALL mysql.rds_innodb_buffer_pool_dump_now();
```
For more information on MySQL events, see [Event Syntax](https://dev.mysql.com/doc/refman/5.6/en/events-syntax.html) in the MySQL documentation\. 

### Dumping and Loading the Buffer Pool on Demand<a name="MySQL.Concepts.InnoDBCacheWarming.OnDemand"></a>

For MySQL version 5\.6\.19 and later, you can save and load the InnoDB cache "on demand\."
+ To dump the current state of the buffer pool to disk, call the [mysql\.rds\_innodb\_buffer\_pool\_dump\_now](mysql_rds_innodb_buffer_pool_dump_now.md) stored procedure\.
+ To load the saved state of the buffer pool from disk, call the [mysql\.rds\_innodb\_buffer\_pool\_load\_now](mysql_rds_innodb_buffer_pool_load_now.md) stored procedure\.
+ To cancel a load operation in progress, call the [mysql\.rds\_innodb\_buffer\_pool\_load\_abort](mysql_rds_innodb_buffer_pool_load_abort.md) stored procedure\.

## Local Time Zone for MySQL DB Instances<a name="MySQL.Concepts.LocalTimeZone"></a>

By default, the time zone for an RDS MySQL DB instance is Universal Time Coordinated \(UTC\)\. You can set the time zone for your DB instance to the local time zone for your application instead\. 

Local time zone is supported for MySQL versions 5\.5, 5\.6, and 5\.7 only\. 

To set the local time zone for a DB instance, set the `time_zone` parameter in the parameter group for your DB instance to one of the supported values listed later in this section\. When you set the `time_zone` parameter for a parameter group, all DB instances and Read Replicas that are using that parameter group change to use the new local time zone\. For information on setting parameters in a parameter group, see [Working with DB Parameter Groups](USER_WorkingWithParamGroups.md)\. 

After you set the local time zone, all new connections to the database reflect the change\. If you have any open connections to your database when you change the local time zone, you won't see the local time zone update until after you close the connection and open a new connection\. 

You can set a different local time zone for a DB instance and one or more of its Read Replicas\. To do this, use a different parameter group for the DB instance and the replica or replicas and set the `time_zone` parameter in each parameter group to a different local time zone\. 

If you are replicating across regions, then the replication master DB instance and the Read Replica use different parameter groups \(parameter groups are unique to a region\)\. To use the same local time zone for each instance, you must set the `time_zone` parameter in the instance's and Read Replica's parameter groups\. 

When you restore a DB instance from a DB snapshot, the local time zone is set to UTC\. You can update the time zone to your local time zone after the restore is complete\. If you restore a DB instance to a point in time, then the local time zone for the restored DB instance is the time zone setting from the parameter group of the restored DB instance\. 

You can set your local time zone to one of the following values\. 


****  

|  |  |  | 
| --- |--- |--- |
| `Africa/Cairo` | `Asia/Bangkok` | `Australia/Darwin` | 
| `Africa/Casablanca` | `Asia/Beirut` | `Australia/Hobart` | 
| `Africa/Harare` | `Asia/Calcutta` | `Australia/Perth` | 
| `Africa/Monrovia` | `Asia/Damascus` | `Australia/Sydney` | 
| `Africa/Nairobi` | `Asia/Dhaka` | `Brazil/East` | 
| `Africa/Tripoli` | `Asia/Irkutsk` | `Canada/Newfoundland` | 
| `Africa/Windhoek` | `Asia/Jerusalem` | `Canada/Saskatchewan` | 
| `America/Araguaina` | `Asia/Kabul` | `Europe/Amsterdam` | 
| `America/Asuncion` | `Asia/Karachi` | `Europe/Athens` | 
| `America/Bogota` | `Asia/Kathmandu` | `Europe/Dublin` | 
| `America/Caracas` | `Asia/Krasnoyarsk` | `Europe/Helsinki` | 
| `America/Chihuahua` | `Asia/Magadan` | `Europe/Istanbul` | 
| `America/Cuiaba` | `Asia/Muscat` | `Europe/Kaliningrad` | 
| `America/Denver` | `Asia/Novosibirsk` | `Europe/Moscow` | 
| `America/Fortaleza` | `Asia/Riyadh` | `Europe/Paris` | 
| `America/Guatemala` | `Asia/Seoul` | `Europe/Prague` | 
| `America/Halifax` | `Asia/Shanghai` | `Europe/Sarajevo` | 
| `America/Manaus` | `Asia/Singapore` | `Pacific/Auckland` | 
| `America/Matamoros` | `Asia/Taipei` | `Pacific/Fiji` | 
| `America/Monterrey` | `Asia/Tehran` | `Pacific/Guam` | 
| `America/Montevideo` | `Asia/Tokyo` | `Pacific/Honolulu` | 
| `America/Phoenix` | `Asia/Ulaanbaatar` | `Pacific/Samoa` | 
| `America/Santiago` | `Asia/Vladivostok` | `US/Alaska` | 
| `America/Tijuana` | `Asia/Yakutsk` | `US/Central` | 
| `Asia/Amman` | `Asia/Yerevan` | `US/Eastern` | 
| `Asia/Ashgabat` | `Atlantic/Azores` | `US/East-Indiana` | 
| `Asia/Baghdad` | `Australia/Adelaide` | `US/Pacific` | 
| `Asia/Baku` | `Australia/Brisbane` | `UTC` | 

## Known Issues and Limitations for MySQL on Amazon RDS<a name="MySQL.Concepts.KnownIssuesAndLimitations"></a>

There are some known issues and limitations for working with MySQL on Amazon RDS\. For more information, see [Known Issues and Limitations for MySQL on Amazon RDS](MySQL.KnownIssuesAndLimitations.md)\. 