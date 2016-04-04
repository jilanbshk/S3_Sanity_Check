# S3 bucket sanity check for Windows CLI.
Simple sanity (public access) check for Amazon-S3 bucket.

Features:
 - Checks if given Amazon-S3 bucket is publicly accessible or not.
 - No need for Amazon AWS CLI
 - Works from your OS Windows desktop (command line)
 - It's executable (s3sanity.exe)  - no need for Python install
 - It's 32 bit - it will work on any vanilla Windows.
 - No AWS Access Keys needed. 
 - Written using Python/boto/PyInstaller

##Version

OS|Platform|Version 
---|---|---- | -------------
Windows|32bit|[0.1.0 beta]

##Purpose

- `s3sanity` helps you confirm that given bucket is not publicly accessible.
- Helps you find readable bucket on Amazon-S3 (for fun).

## How it works
- s3sanity.exe tries to read given bucket from Amazon-S3.
- Prints `success` message if bucket is publicly accessible (readable).
- Prints `error` message if bucket does not exists or not readable.
- It will not elaborate why read try faied.

##Audience

Database/ETL developers, Data Integrators, Data Engineers, Business Analysts, AWS Developers, DevOps

##Designated Environment
Pre-Prod (UAT/QA/DEV)

##Usage

```
C:\Python35-32>dist\s3sanity.exe
## S3 sanity check.
##
## Outputs access status to the screen.
##
Usage:

  s3_sanity.exe -b <bucket_name>

    -b [--bucket] -- S3 bucket name.


	
"""

```

##Environment variables

* No environment variables required because it's a public access test.


#Examples

###How to check if S3 bucket is publicly readable or not?


####Testing if bucket `test` is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b test
#####################################
NO access OR does NOT exists ("test")
#####################################

```

Bucket `test` does not exist or unreadable by everyone.


####Testing if bucket `test2` is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b test2

You HAVE access to "test2"

```

Horay! Bucket `test2` is readable by everyone!


####Testing if bucket "elvis" is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b elvis
#####################################
NO access OR does NOT exists ("elvis")
#####################################

```

Too bad. Bucket `elvis` does not exist or unreadable by everyone.


####Testing if bucket "refuse" is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b refuse

You HAVE access to "refuse"

```

Horay! Bucket `refuse` is readable by everyone!




##Download
* [Master Release](https://github.com/alexbuz/S3_Sanity_Check/archive/master.zip) -- `s3sanity 0.1.0`
* 


#FAQ
#  
#### Can it tell if S3 bucket is unreadable?
No, it cannot really tell if it's unreadable or simply does not exists.

#### Do I need a password to use it?
No, no passwords or access keys.
We are testing public read access to a bucket.

#### How does it work?
I use Python boto (AWS API for Python) module to interact with AWS.
Boto checks header of the bucket. If successful - it's readable.
```
s3.meta.client.head_bucket(Bucket=bucket.name)
```

#### What are the other ways to do it?
You can use AWS CLI `aws s3api` to do the same.


#### Can I check multiple buckets for readability?
No. To do you have to call `s3sanity.exe` for each S3 bucket.

#### Does check contents of the bucket for readability?
No

#### Does it create any manifest files?
No

#### Can I use Linux.
No, only OS Windows for now.

#### What technology was used to create this tool
I used Python and Boto (AWS API for Python) to write it.

#### Where are the sources?
Please, contact me for sources.

#### Can you modify functionality and add features?
Yes, please, ask me for new features.

#### What other AWS tools you've created?
- [CSV_Loader_For_Redshift] (https://github.com/alexbuz/CSV_Loader_For_Redshift/blob/master/README.md) - Append CSV data to Amazon-Redshift from Windows.
- [EC2_Metrics_Plotter](https://github.com/alexbuz/EC2_Metrics_Plotter/blob/master/README.md) - plots any CloudWatch EC2 instance  metric stats.
- [S3_File_Uploader](https://github.com/alexbuz/S3_File_Uploader/blob/master/README.md) - uploads file from Windows to S3.

#### Do you have any AWS Certifications?
Yes, [AWS Certified Developer (Associate)](https://raw.githubusercontent.com/alexbuz/FAQs/master/images/AWS_Ceritied_Developer_Associate.png)

#### Can you create similar/custom data tool for our business?
Yes, you can PM me here or email at `alex_buz@yahoo.com`.
I'll get back to you within hours.

###Links
 - [Employment FAQ](https://github.com/alexbuz/FAQs/blob/master/README.md)
 - 
 
