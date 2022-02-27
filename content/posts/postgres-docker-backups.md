---
title: "Automated Postgres Backups using Docker"
date: 2022-02-27T04:37:49-06:00
draft: false
---

This section we’ll go over running backups for postgres running in docker.

A few things, since I am running rclone as the backend for the filesystem here, we can’t do hardlinks.

My docker image here, https://hub.docker.com/r/tehsu/docker-postgres-backup-local is built with a cp rather than a symlink.

I plan to add checks to see if hardlinks are available, if they are then we’d continue to use symlinks otherwise we’d need to copy the file.
