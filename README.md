# S3 bucket sanity check.

Simple sanity check for s3 bucket.
Detects if you have public access to give S3 bucket or not.


Written using Python/boto3/PyInstaller

##Version

OS|Platform|Version 
---|---|---- | -------------
Windows|32bit|[0.1.0 beta]

##Purpose

- Helps you to confirm that given bucket is publickly accessible.

## How it works
- s3sanity.exe tries to read given bucket for Amazon-S3.
- Prints success message if bucket is publicly accessible (readable).
- Prints error message if bucket does not exists or not readable.
- It will not elaborate why read try faied.

##Audience

Database/ETL developers, Data Integrators, Data Engineers, Business Analysts, AWS Developers, DevOps, 

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


##Example sanity checks


* Testing if bucket `test` is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b test
#####################################
NO access OR does NOT exists ("test")
#####################################

```

Bucket `test` does not exists or unreadable by everyone.


* Testing if bucket `test2` is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b test2

You HAVE access to "test2"

```

Horay! Bucket `test2` is readable by everyone!


* Testing if bucket "elvis" is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b elvis
#####################################
NO access OR does NOT exists ("elvis")
#####################################

```

Too bad. Bucket `elvis` does not exists or unreadable by everyone.


* Testing if bucket "refuse" is readable by everyone.

```
C:\Python35-32>dist\s3sanity.exe -b refuse
#####################################
NO access OR does NOT exists ("refuse")
#####################################

```

Too bad. Bucket `refuse` does not exists or unreadable by everyone.




##Download
* [Master Release](https://github.com/alexbuz/S3_Sanity_Check/archive/master.zip) -- `s3sanity 0.1.0`
