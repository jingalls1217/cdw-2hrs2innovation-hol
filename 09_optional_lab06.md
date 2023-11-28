## Optional Lab 6 - Iceberg Table Rollback 

This lab will quickly show you how to do a **Rollback** to a specific **Snapshot**, a key feature of Iceberg tables, with other maintenance tasks that can be performed as well.

### Iceberg Rollback [Table Maintenance]

Sometimes data can be loaded incorrectly, due to many common issues - missing fields, only part of the data was loaded, bad data, etc.  In situations like this, data would need to be removed, corrected, and reloaded. Iceberg can help with the Rollback command to remove the “unwanted” data. This leverages Snapshot IDs to perform this action by using a simple `ALTER TABLE` command as follows. We **_will not_** run this command in this lab

```
-- ALTER TABLE ${user_id}_airlines.flights EXECUTE ROLLBACK(${snapshot_id});
```

### Iceberg Expire Snapshots [Table Maintenance]

As time passes, it might make sense to expire old Snapshots. Instead of the Snapshot ID, you use the Timestamp to expire old Snapshots. This can be done manually by running a simple `ALTER TABLE` command as follows. We **_will not_** run this command in this lab

```
-- Expire Snapshots up to the specified timestamp 

-- BE CAREFUL: Once you run this you will not be able to Time Travel for any Snapshots that you Expire 

-- ALTER TABLE ${user_id}_airlines.flights 

-- ALTER TABLE ${user_id}_airlines_maint.flights EXECUTE expire_snapshots('${create_ts}');
```