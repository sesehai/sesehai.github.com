---
layout: post
category : 技术
tagline: ""
tags : [stackedit.io]
title : 【transfer】Log rotation directly within Nginx configuration file
author: SSH
---

Ever since I discovered PostgreSQL allowed to embed variables in log_filename allowing to split logs without using logrotate or cronolog, I’ve been wanting to do the same with Nginx.

As it turns out, it’s not only possible but also pretty easy to achieve, since **Nginx** introduced the possibility to use **variables in access_log** directives (added in 0.7.4), and the **$time_iso8601** variable providing time in ISO 8601 format (added in 0.9.6).

Please note, that it’s not possible to embed **variables in error_log** directives, as any potential error would not be able to be logged if the file cannot be written.

Here is an example showing $time_iso8601 format :

    2014-05-04T18:12:02+02:00

All there is to do is use an “if” block to split required data using a regular expression and set time variables.

For splitting logs by day, one would use the following snippet in the server block :

    if ($time_iso8601 ~ "^(\d{4})-(\d{2})-(\d{2})") {
        set $year $1;
        set $month $2;
        set $day $3;
    }
    
    access_log /var/log/nginx/$year-$month-$day-access.log;

Alternatively, we can also use the Perl compatible syntax for named regular expression capture :

    if ($time_iso8601 ~ "^(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})") {}
    
    access_log /var/log/nginx/$year-$month-$day-access.log;

To also create variables for hours, minutes and seconds, we can use the following snippet :

    if ($time_iso8601 ~ "^(\d{4})-(\d{2})-(\d{2})T(\d{2}):(\d{2}):(\d{2})")
    {
        set $year $1;
        set $month $2;
        set $day $3;
        set $hour $4;
        set $minutes $5;
        set $seconds $6;
    }

Lastly, and I cannot stress it enough, please make sure the Nginx workers have proper permissions to access and write to the log directory.

This method is currently used in production on a busy Nginx server and has been running flawlessly for almost a month now. The only drawback is that buffered writes do not work when the access_log file path contain variables, so it isn’t possible to gzip logs on the fly.

[source >>](http://www.cambus.net/log-rotation-directly-within-nginx-configuration-file/)