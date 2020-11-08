# Hitachi
Hitachi Interview solution

AWS S3 buckets can be configured to replicate all objects put in them to another bucket in a different region. This is called Cross Region Replication.

Why this is useful is that objects stored in a bucket are kept only in the region that they were created in. Other regions may be able to access them if allowed but if a regional outage were to occur the contents of the buckets in that region may not be accessible.

Note that because S3 buckets have a global namespace it is not possible to have a bucket with the same name in 2 different regions.

Because of this it is useful to name a bucket with a suffix of the region that the bucket was created in. Doing that allows you to have uniquely named buckets that differ in name by only the region making the functions accessing the contents easier to write and manage.

How to implement the soultion:

Run the attached .yml file in order of sequence as , first the Backup bucket need to be created using "Replicated_Bucket_Encrypted.yml", and later the same ARN need to be copied and the Source bucket with Replication Rule need to be created in different region using, "Source_Bucket_Encrypted.yml".

Once the buckets are created in two different regions, then you can test the file by placing it in SourceBucket.

Note: The files with the naming convention 'log.datxxxxxx' will only be processed as per the configuration.

Sample file is also attached which need to be tested.
