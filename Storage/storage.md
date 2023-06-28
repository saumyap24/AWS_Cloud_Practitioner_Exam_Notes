- [Types of Storage Services](#types-of-storage-services)
- [Introduction to S3](#introduction-to-s3)

---
## Types of Storage Services
---
- <b> Elastic Block Store </b> (Block):
    - Data is split into evenly split blocks directly accessed by OS supports only a single write volume
    - Scenario: When you need a virtual hard drive attached to a VM
        <img src="../images/Storage/Elastic_block_store.png" width="40%"/> 
- <b>  AWS Elastic FIle Storage (EFS) </b> - (File)
    - File is stored with data and metadata 
    - Multiple connections via a network share 
    - Supports multiple reads, writing locks the file
    - Scenario: When you need a file-share where multiple users or VMs need to access the same drive 
    <img src="../images/Storage/Elastic_File_Storage.png" width="40%"/>

- Amazon <b> Simple Storage Service (S3) </b> - (Object)
    - Object is stored with data, metadata and Unique ID
    - Scales with limited no file limit or storage limit
    - Supports multiple reads and writes (no locks)
    - Scenario: When you just want to upload files and not have to worry about underlying infrastructure. Not intended for high IOPs.

        <img src="../images/Storage/S3.png" width="40%"/>

---
## Introduction to S3
---

- <b> What is Object Storage (Object-based storage)? </b>
- data storage architecture that manages data as objects, as opposed to other storage architectures:
    - file systems: which manages data as files and fire hierarchy
    - block storage- which manages data as blocks within sectors and tracks
        - S3 provides with <u> Unlimited storage </u>
        - Need not think about underlying infrastructure
        - S3 console provides an interface for you to upload and access your data 

| **S3 Object**                                                           | **S3 Bucket**                                                           |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| - Obejcts contain data(files)                                           | - Buckets hold objects                                                  |
| - Object may consists of:                                               | - Buckets can have folders which can turn in hold objects               | 
|   - <b> Key </b> this is the name of the object                         | - S3 is universal namespace so domain names must be <u> Unique </u>     | 
|   - <b> Value </b> data iteself is made up of sequence of bytes         |
|   - <b> Version Id </b> version of object (when versioning is enabled)  |
|   - <b> Metadata </b> additional information attached to the object     | 

