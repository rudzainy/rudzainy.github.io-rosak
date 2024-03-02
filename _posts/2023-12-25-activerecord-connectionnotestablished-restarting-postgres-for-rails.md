---
layout: post
title: 'ActiveRecord::ConnectionNotEstablished: Restarting Postgres for Rails'
date: 2023-12-25 08:46 +0800
description: How to resolve ActiveRecord ConnectionNotEstablished error by restarting Postgres for Rails.
image: /assets/img/posts/Screenshot_2023-12-25_at_9.34.08_AM.png
category: Work
tags: [rails, postgres, error]
published: true
sitemap: true
---

Last night I encountered this error message while building [Ranting](/posts/ranting):

```bash
ActiveRecord::ConnectionNotEstablished (connection to server on socket "/tmp/.s.PGSQL.5432" failed: No such file or directory
        Is the server running locally and accepting connections on that socket?
):
```


I vaguely remember encountering this error message a while back 🤔. I'm not certain what actually caused the error, however I figured restatrting Postgress would solve this. Here's how to do it.


## 1. Look for Postgres Installation

My current setup has Postgres installed with Homebrew.

```bash
  $ brew list
  ==> Formulae
  ...
  cairo         liblqr          poppler
  coreutils     libnghttp2      postgresql@14
  docbook       libomp          protobuf
  ...
```

Seems that I have `postgresql@14` installed.

## 2. Restart Postgres

Now, navigate to this folder:

```bash
  $ cd /usr/local/var
```

Look for the same Postgres installation folder as in Homebrew list above.

```bash
  $ ls
  cache		homebrew	mysql		run
  db		log		postgresql@14
```

`cd` into the Postgres folder and look for a file called `postmaster.pid`.

```bash
  $ cd postgresql@14 
```

```bash
  $ ls
  PG_VERSION		pg_ident.conf		pg_snapshots		pg_wal
  base			pg_logical		pg_stat			pg_xact
  global                pg_multixact            pg_stat_tmp             postgresql.auto.conf
  pg_commit_ts		pg_notify		pg_subtrans		postgresql.conf
  pg_dynshmem		pg_replslot		pg_tblspc		postmaster.opts
  pg_hba.conf		pg_serial		pg_twophase		postmaster.pid
  
```

Found it! Next, backup the `postmaster.pid` file to another folder (eg. the Desktop folder) and restart Postgres.

```bash
  $ mv postmaster.pid ~/Desktop
```

```bash
  $ brew services restart postgresql@14
  Stopping `postgresql@14`... (might take a while)
  ==> Successfully stopped `postgresql@14` (label: homebrew.mxcl.postgresql@14)
  ==> Successfully started `postgresql@14` (label: homebrew.mxcl.postgresql@14)
```

## 3. Move On with Life

Run Rails server again and that should resolve the error. 

It should be safe now to delete the `postmaster.pid` that was backed up earlier.