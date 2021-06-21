release: bash ./.deploy/commands/check_last_commit_status.sh && bash ./.deploy/commands/check_commits_stats.sh && bash ./.deploy/commands/backup_database.sh && php artisan migrate --force && bash ./.deploy/commands/triggerSmokeTests.sh
web: vendor/bin/heroku-php-apache2 public/
worker: php artisan queue:listen --tries=1 --timeout=7200 --queue=high,medium,default,low
