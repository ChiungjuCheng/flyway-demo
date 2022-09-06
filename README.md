# Flyway

## How to run
    mvn  flyway:migrate

### log
```text
user@user-system:~/Projects/flyway-demo$ mvn  flyway:migrate
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< org.example:flyway-demo >-----------------------
[INFO] Building flyway-demo 1.0-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- flyway-maven-plugin:9.2.2:migrate (default-cli) @ flyway-demo ---
[INFO] Flyway Community Edition 9.2.2 by Redgate
[INFO] See what's new here: https://flywaydb.org/documentation/learnmore/releaseNotes#9.2.2
[INFO] 
[INFO] Database: jdbc:mysql://<host>:3307/mydb (MySQL 8.0)
[INFO] Successfully validated 1 migration (execution time 00:00.009s)
[INFO] Current version of schema `mydb`: 1
[INFO] Schema `mydb` is up to date. No migration necessary.
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.489 s
[INFO] Finished at: 2022-09-07T00:54:59+08:00
[INFO] ------------------------------------------------------------------------

```
### flyway_schema_history
```shell
mysql> select * from flyway_schema_history;
+----------------+---------+---------------------+------+-----------------------------+------------+--------------+---------------------+----------------+---------+
| installed_rank | version | description         | type | script                      | checksum   | installed_by | installed_on        | execution_time | success |
+----------------+---------+---------------------+------+-----------------------------+------------+--------------+---------------------+----------------+---------+
|              1 | 1       | Create person table | SQL  | V1__Create_person_table.sql | 1715188512 | root         | 2022-09-06 16:38:15 |            136 |       1 |
+----------------+---------+---------------------+------+-----------------------------+------------+--------------+---------------------+----------------+---------+
1 row in set (0.00 sec)

```