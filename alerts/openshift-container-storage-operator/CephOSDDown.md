# CephOSDDown

## Meaning

OSD (Object Storage Daemon) are down indicates ceph-osd daemons not running as expected.

## Impact

**Severity:** Warning
**Potential Customer Impact:** Medium

This alert suggests that one or more OSDs might be down.

## Diagnosis

The alert is triggered when Ceph OSD(s) is/are down, please check the ceph-osd daemons and take corrective measures.

## Mitigation

### Recommended Actions

1. In an LSO cluster, if the disk failed, the OSD may need to be replaced. Please ref:
[Instructions for safely replacing operational or failed devices](https://docs.redhat.com/en/documentation/red_hat_openshift_data_foundation/4.17/html-single/replacing_devices/index)

2. To investigate why one or more OSDs are marked down. The ceph-osd daemon(s) or their host(s) may have crashed or been stopped, or peer OSDs might be unable to reach the OSD over the public or private network. Common causes include a stopped or crashed daemon, a “down” host, or a network failure.

Verify that the host is healthy, the daemon is started, and the network is functioning. If the daemon has crashed, the daemon log file (/var/log/ceph/ceph-osd.*) may contain troubleshooting information.
