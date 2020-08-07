---
title: Laravel DB Commands Package
subtitle: A few Artisan commands to help with everyday database tasks.
category: code
description: A few Artisan commands to help with everyday database tasks.
keywords: laravel, artisan, database tasks
---
As much as I hate leaving terminal and entering into the bright
draggable clickable GUI, I also despise writing lengthy commands over
and over again. I found myself doing both of these things for a few
different database tasks and decided enough was a enough: Time for a
package!

I whipped together a collection of Artisan commands that help with
common MySQL tasks. Let's see what we've got.

### DB Pull:
I am pulling a database atleast once a day. Remembering the database
credentials is too much to do it on the command line everytime, and I am
tired of pulling it from Sequel Pro. After a little configuration, a
simple `php artisan db:pull production` pulls down the production
database and imports it into my local machine. Easy peasy!

### DB Test Prepare:
When starting an app or building out new features, having to re-run
migrations and/or seeds for every database change can become a bit
tedious. Inspired by a Rails command, `php artisan db:test-prepare`,
refreshes my testing database and re-run seeds if I want. Simple!

### DB Backup:
Seeing as how easy Artisan makes scheduling tasks, I wrote a command to
dump the database and sync it to a cloud storage disk. I use S3, but it
should work with any disk Laravel supports. Drop a little
`$schedule->command('db:backup')->twiceDaily();` in your Console Kernel,
and boom! Backups twice a day!

You can find the repo and specifics on configuring it here:
[Github](https://github.com/nobodyiscertain/laravel-db-commands)

Hoping these save a little time in your day!
