Yas3fs Monit
=========

An ansible role that mounts S3 buckets locally using yas3fs and after that sets up monit in order to watch for any S3 unmount and mount it back.
It should be run on an EC2 instance that has an instance profile with S3 rw access attached. If you want to run this on an instance without profile then you need to setup aws cli.

Requirements
------------

This role can be run on Ubuntu Server. It was tested on Ubuntu 18.06.

Role Variables
--------------

There are several variables that should be set and overriden for this role.

* aws_sns_topic_arn: topicarnhere
* aws_sqs_queue_name: sqsnamehere
* aws_region: awsregionhere
* mounts:
   - user: user1  
      dir: dir1  
      s3_bucket_path: s3://sftp-bucket/dir1  
      fs_directory: /sftp/user1/dir1  
 
```
---
aws_sns_topic_arn: topicarnhere
aws_sqs_queue_name: sqsnamehere
aws_region: awsregionhere
mounts:
  - user: user1
    dir: dir1
    s3_bucket_path: s3://sftp-bucket/dir1
    fs_directory: /sftp/user1/dir1
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: sftp
      roles:
         - { role: alexjgui.yas3fs_monit, tags: yas3fs }

License
-------

None
