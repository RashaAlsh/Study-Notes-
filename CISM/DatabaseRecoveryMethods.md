Database Recovery Methods

1. Electronic Vaulting

* Backups are transferred to an off-site facility periodically (e.g., daily or every few hours).
* Sends the entire modified file, not just the changes.
* Recovery: Slower, as recent updates may not be included in the latest backup.

2. Remote Journaling

* Backup data is transmitted frequently or in real time to a remote site.
* Sends only deltas (individual changes or transactions) instead of entire files.
* Recovery: Faster and more efficient, with less potential data loss.

3. Remote Mirroring

* Maintains a live standby database server at a remote backup site.
* All changes to the primary database are replicated in real time.
* Enables rapid failover if the primary site fails.
* Recovery: Fastest recovery, but typically the most expensive option; ideal for a hot site.

Quick Comparison

Method	Transfer Frequency	Data Transferred	Recovery Speed	Cost
Electronic Vaulting	Periodic	Entire modified files	Slower	Lower
Remote Journaling	Frequent / Real-time	Changes / Transactions	Faster	Medium
Remote Mirroring	Real-time	Continuous replication	Fastest	Highest

Key takeaway: Electronic vaulting sends files in batches, remote journaling sends changes frequently, and remote mirroring continuously replicates a live database for rapid failover.