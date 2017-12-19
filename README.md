# docker-apache-php-base-trigger

This repo builds a pointless docker image that just contains this readme.

This repo is auto-build triggered by the `php` repo. Whenever this repo builds,
we then call a webhook which checks if php7.1-apache has changed, if it has we
then manually trigger `shanemcc/docker-apache-php-base` to rebuild.

This means we don't end up rebuilding a billion times whenever PHP changes
something in any repo we don't care about.
