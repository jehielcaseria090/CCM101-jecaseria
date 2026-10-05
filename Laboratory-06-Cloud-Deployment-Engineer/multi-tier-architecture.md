# Two-Tier Architecture

A two-tier architecture splits an application into a web/application tier that
users interact with and a database tier that stores the data.

## The Web/Application Tier
This tier serves the user interface and handles HTTP requests. In this lab, the
Nextcloud container is the web/application tier. It handles logins, uploads, and
page requests, and asks the database for data when needed.

## The Database Tier
This tier stores persistent data such as user accounts, credentials, and file
metadata. In this lab, the MariaDB container is the database tier.

## Why Separate Them?
Separate containers can be updated, restarted, scaled, or fixed independently
without affecting each other. It also improves security, because the database is
not exposed publicly, and the data stays safe if the web container is replaced.
