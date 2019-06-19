# Storage Scan

It is common to have large data sets partitioned across large number of hosts or databases or having billions of files in an S3 bucket.
Cadence is an ideal solution for implementing the full scan of such data in a scalable and resilient way. The standard pattern 
is to run an activity (or multiple parallel activities for partitioned data sets) that performs the scan and heartbeats its progress
back to Cadence. In a case of a host failure the activity is retried on a different host and continues execution from the last reported progress. 
