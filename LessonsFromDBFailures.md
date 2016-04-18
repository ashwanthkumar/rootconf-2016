# Lessons from DB failures

By Colin Charles, MariaDB 

- Backups (and verification)
- Replication (and failover)


- Don't use HFS
- Don't use `rsync` for taking backup of dynamic data

- Self-hosted
    - xtrabackup - Similar to InnoDB but a different Engine
    - `START TRANSACTION WITH CONSISTENT SNAPSHOT + mysqldump -single-transaction -master-data`
    - Backup a replica
    - Replication event checksums - Make sure you don't replicate crap
        - Row based replication instead of statement based replication

- Time-delayed replication
    - MySQL 5.6+ has time-delayed replication. Stop replication when you know a mistake has happened before it propogates to all the slaves.

- Why Replicate?
    - Scale out
    - [automatic] (master) failover
    - Geo redundancy across multiple DCs
    - Online schema changes
        - PG online schema changes
- Replication
    - Async (default)
    - Semi-sync (plugin) - Used by Google and FB
        - Loss less semi-sync - Doesn't get affected by phantom reads
    - Sync - used in NDBCLUSTER
    - DRBD - Distributed Raid block device
- Frameworks
    - MySQL-MMM - Don't use it
    - Severalnines ClusterControl
    - Orchestrator
    - MySQL MHA - MySQL High Availability
    - Tungesten Replicator
    - 5.6+ Utilities
        - mysqlfailover
        - mysqlrpladmin
    - Percona Replication Manager
    - MariaDB Replication Manager

- Github decided to move away from Automatic failover

- Proxies
    - MariaDB MaxScale - Load balance Galera clusters
    - MySQL Router + MySQL Fabric
    - ProxySQL

- Sharding
    - SPIDER
    - Tugsten Replicator
    - Tumblr JetPants
    - Vitess - Battle tested
