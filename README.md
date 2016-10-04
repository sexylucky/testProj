# testProj
-- Repair/Cleanup Fun:
nodetool repair > /log/location (For Full Cluster Repair)
nodetool repair -pr > /log/location (For Partial Repair)
nodetool cleanup > /log/location (Clean Up after repair)

-- Any EBS Volume Snapshot
nodetool flush;
ruby /Installed/ebs-snapper/location/ebs-snapper-0.0.5/lib/ebs-snapper.rb -d /our/mount -r x(Total SnapShots to retain)

-- Older Version Mandatory Conf
Cassandra.yaml (Usually Default is Good Enough with other conf's)
cluster_name
multithreaded_compaction
concurrent_writes
concurrent_reads
rpc_address
listen_address
data_file_directories
commitlog_directory
seeds
initial_tokens
incremental_backups

cassandra-rackdc.properties (This will help in lot of scenarios, like Multi-DC DR setup cluster and replication between clusters)
dc=
rac=

Cassandra-env.sh
max_heap_size
heap_newsize
additional_jvm_opts and also other JVM optimization related conf's

cassandra-topology.properties
IP/Hostname=Data Center:Rack
