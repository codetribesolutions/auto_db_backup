# auto_db_backup
Automatized daily/weekly/periodic MySQL backups to AWS S3 buckets and gDrive.

If you are not using RDS to host your databases, it is very probable that you are doing your own backups. In this article we'll see a very simple shell script to do automatic daily backups for your mysql databases into an S3 bucket or gDrive.

----------------------------------------------

*Step 1* : Set your AWS key ID or secret and MySQL connection credentials. 

AWS_ACCESS_KEY_ID=my_key \
AWS_SECRET_ACCESS_KEY=my_secret \
AWS_DEFAULT_REGION=us-west-2 \
S3_BUCKET=my_bucket \
MYSQL_HOST=host \
MYSQL_PORT=port \
MYSQL_USER=myuser \
MYSQL_PASS=pass \
MYSQL_DB=db 

*Step 2* : Following are the steps for how to use in project.

1.) Composer require codetribesolutions/auto_db_backup \
2.) add auto_db_backup/Db2CloudServiceProvider.php in app.php \
3.) php artisan vendor:publish --tag=backupconfig \
4.) Change app/backupconfig.php file of your project \
5.) php artisan db:Backup 

*Step 3* : Set a Cron Job ( Cron is a standard Linux feature that allows you to schedule tasks )

----------------------------------------------

Hopefully this will help you automate your daily backups for you database.

