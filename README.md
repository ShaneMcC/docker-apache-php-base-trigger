# dockerhub-rebuild-trigger

This repo builds a pointless docker image that just contains this readme.

This repo is auto-build triggered by numerous other repos on dockerhub.
Whenever this repo builds, we then call a webhook which checks if the specific
tags we care about have changed (eg, this repo depends on `php`, but we only
actually care if php:7.1-apache has changed).

If what we care about has changed we then manually trigger other repos to
rebuild as needed.

This means we don't end up rebuilding a billion repos a billion times whenever
PHP changes something and ends up rebuilding a billion tags.

At some point I'll put the hook code here as well for completeness.
