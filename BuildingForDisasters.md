# Building for Disasters: approach to robust systems

DR - Disaster Recovery

DR is not Backup
DR is not HA (High Availability)

DR is little different.

## Notes

- Understand the scope of your DR
- Traditional way of DR is having another site some 500kms away with smaller compute capacity. 
- DR is of no use until we test them often
- Data synchronization and application consistency is very very important

### 7 Tiers of DR

##### Backups
- Tier 0 - No off-site disaster recovery plan
- Tier 1 - Data backup with no hot site
- tier 2 - Data backup with hotsite

##### Electronic Disk based backups
- Tier 3 - Electronic Vaulting
- Tier 4 - Point-in-time copies
- Tier 5 - Transaction integrity

##### Part 3 - Not sure what's the name of this section
- Tier 6 - Zero or near-zero data loss
- Tier 7 - Highly automated business integrated soution

RPO - Recovery point object
RTO - Recovery Time object

> Test Failure - measure and improve
