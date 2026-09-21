# Mission 5 Reflection
Object storage is better than block storage for saving millions of photos because Object storage can grow easily. Block storage is tied to one disk and one computer so block storage has limits on space and speed once many files are added. Object storage saves each photo as its file with extra details attached and Object storage can be accessed straight from the internet. Object storage makes it much easier to handle a number of photos without slowing down or running out of room.

Using Docker made deploying MinIO much easier and faster. Of installing MinIO manually and setting up all its settings by hand I only needed one command to download MinIO start MinIO and set the login details using environment variables. Docker also kept MinIO from the rest of the system so Docker did not affect anything else running on the machine.

A bucket in storage is like a folder or container where objects (files) are kept. Every file uploaded to object storage must be placed inside a bucket. Each bucket usually has its own name and access settings. In this lab I created a bucket named `client-photos` to hold the uploaded images.

Large companies keep their object storage safe by copying data across servers and even multiple locations. This is called replication. If one server or data center fails the data is still available from another copy. Companies also use backups and monitoring tools to check that all copies stay in sync and nothing is lost.

My confidence, in using the Linux command line is growing. At first running commands felt confusing. After doing several labs I am becoming more comfortable typing commands, understanding what they do and fixing small mistakes when something does not work. I feel more confident exploring commands and trying things without being afraid of breaking something.
