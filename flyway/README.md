# Flyway migrations (Oracle)

This folder contains Flyway configuration and SQL migration files for Oracle.

Structure:
- conf/flyway.conf  - Flyway configuration
- sql/              - Versioned SQL migrations (V1__, V2__, ...)

How to run:
- Using Docker Compose in `../docker/` (runs Flyway and connects to your Oracle DB)
- Or run Flyway CLI: `flyway -configFiles=conf/flyway.conf migrate`

Ensure `flyway.conf` points at your Oracle instance (SID/service name) and that the Oracle listener is reachable.
