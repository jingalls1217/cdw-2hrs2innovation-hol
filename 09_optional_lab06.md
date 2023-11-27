## Optional Lab 6 - Iceberg Table Rollback 

This lab will shows you how to do a Rollback to a specific Snapshot.  This is a key feature of Iceberg tables.  There are other Maintenance Tasks that you can perform on Iceberg tables.

27. Iceberg Rollback \[Table Maintenance] - sometimes data can be loaded incorrectly, due to many common issues - missing fields, only part of the data was loaded, bad data, etc.  In situations like this data would need to be removed, corrected and reloaded.  Iceberg can help with the Rollback command to remove the “unwanted” data.  This leverages Snapshot IDs to perform this action by using a simple ALTER TABLE command as follows.  We **_will not_** run this command in this lab

<!---->

    -- ALTER TABLE ${user_id}_airlines.flights EXECUTE ROLLBACK(${snapshot_id});

28. Iceberg Expire Snapshots \[Table Maintenance] - as time passes it might make sense to expire old Snapshots, instead of the Snapshot ID you use the Timestamp to expire old Snapshots.  You can do this manually by running a simple ALTER TABLE command as follows.  We **_will not_** run this command in this lab

<!---->

    -- Expire Snapshots up to the specified timestamp 

    -- BE CAREFUL: Once you run this you will not be able to Time Travel for any Snapshots that you Expire ALTER TABLE ${user_id}_airlines.flights 

    -- ALTER TABLE ${user_id}_airlines_maint.flights EXECUTE expire_snapshots('${create_ts}');

***