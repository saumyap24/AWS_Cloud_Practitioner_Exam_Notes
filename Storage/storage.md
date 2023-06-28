- [Types of Storage Services](#types-of-storage-services)
- [Introduction to S3](#introduction-to-s3)
- [S3 Storage Classes](#s3-storage-classes)
- [AWS Snow Family](#aws-snow-family)

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
        - Individual Object can be store form <u> 0 Bytes to 5 Terabytes </u> in size

| **S3 Object**                                                                   | **S3 Bucket**                                                           |
| ------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| - Obejcts contain data(files)                                                   | - Buckets hold objects                                                  |
| - They are like files                                                           | - Buckets can have folders which can turn in hold objects               |
| Object may consists of:  </br> - <b> Key </b> this is the name of the object </br> - <b> Value </b> data iteself is made up of sequence of bytes   <br>- <b> Version Id </b> version of object (when versioning is enabled) <br> - <b> Metadata </b> additional information attached to the object                                               | - S3 is universal namespace so domain names must be <u> Unique </u>      | 

---
## S3 Storage Classes 
--- 

- AWS offers a range of S3 Storage classes that<u> trade Retrieval, Time, Accessbility and Durability for Cheaper Storage </u>



### (Descending from expensive to cheaper)

<div style="display:flex;">
<img src="../images/Storage/cheaper.png" width="15%" height = 500 float="right" />

<p float="right">

- <b> S3 Standard (default) </b>
    - Fast! 99.99 % Availibility, 
    - 11 9's Durability. 
    - Replicated accross at least thress AZs

- <b> S3 Intelleigent Tiering </b>
    - Uses ML to analyze object usage and determine the approprate storage class
    - Data is moved to most cost-effective tier without any performance impact or added overhead

- <b> S3 Standard-IA (Infrequent Access) </b>
    - Still Fast! Cheaper if you access files less than once a month
    - Additional retrieval fee is applied. 50% less than standard (reduced availability)

- <b> S3 One-Zone-IA </b>
    - Still fast! Objects only exist in one AZ. 
    - Availability (is 99.5%). but cheaper than Standard IA by 20% less

- <b> S3 Glacier </b>
    - For long term cold storage
    - Retrieval of data can take minutes to hours but the off is ver cheap storage

- <b> S3 Glacier Deep Archive </b>
    - The lowest cost storage class
    - Data retrieval time is 12 hours
</p>

</div>

---
## AWS Snow Family
---

- AWS Snow Family are <u> Storage and compute devices used to physically move data in or out the cloud </u> when moving data over the internet or private connection it to slow, difficult or costly

