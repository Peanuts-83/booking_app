# DB backup instructions

Before any touchy change on your DB, you should backup your last stable DB state.

## Save DB

Use mysql uility **mysqldump**, connect to appropriate IP with user (root) and password (myrootpassword).

* Command is launched from host, not from container.
* Target is the database name, no matter the path.
* Destination require path, relative to your cwd.

```bash
# cwd: bookingApp_work_directory/booking_back
mysqldump -h 192.168.168.2 -u root -p mydatabase > ../db_backup/mydatabase_bkp2_newFK.sql
```

## Restore DB

```bash
# cwd: bookingApp_work_directory/booking_back
mariadb mydatabase < ../db_backup/mydatabase<bkp_version>.sql
# OR - not tested yet
mysql mydatabase < ../db_backup/mydatabase<bkp_version>.sql
```
