# Host a Static Website on Amazon S3

## Introducing this Project!

In this project, I hosted a static website on Amazon S3.

### Services Used

- S3

### Concepts Learnt

- Creating an S3 bucket and uploading files & folders in it
- Controlling access to S3 buckets and objects via ACLs
- Static website hosting on S3

### Architecture Diagram

![Image](https://github.com/sumeet15n/host-a-website-on-S3/blob/master/Screenshots/SS0.png)

---

## Project Guide

### Step 1: Create a Bucket in S3

First, I signed into the AWS management console as an IAM user with admin access and not as the root user of my AWS account (best practice), navigated to S3, and set my region as the one closest to my geographical location (ap-south-1) to minimize the latency (another best practice).

Next, I created my bucket with a globally unique bucket name ('nextwork-website-project-sumeetsd'), with ACLs enabled and all public access blocked.

A screenshot of the created bucket is shown below.

![Image](https://github.com/sumeet15n/host-a-website-on-S3/blob/master/Screenshots/SS1.JPG)

### Step 2: Upload Website Content into the Bucket

I uploaded the 'index.html' file and 'NextWork - Everyone should be in a job they love_files' folder into my bucket.

A screenshot of the uploaded objects is shown below.

![Image](https://github.com/sumeet15n/host-a-website-on-S3/blob/master/Screenshots/SS2.JPG)

### Step 3: Enable Static Website Hosting

I navigated to the 'Properties' tab of my bucket and enabled static website hosting, with 'index.html' as the index document, as shown in the below screenshot.

![Image](https://github.com/sumeet15n/host-a-website-on-S3/blob/master/Screenshots/SS3.JPG)

Next, in the 'Static website hosting' panel, I visited the URL under 'Bucket website endpoint'.

Unfortunately, I encountered the '403 Forbidden' error, as shown in the below screenshot.

![Image](https://github.com/sumeet15n/host-a-website-on-S3/blob/master/Screenshots/SS4.JPG)

This error was encountered because bucket objects are private by default for security. The static website was being hosted by S3, but the actual HTML and assets files were still private (i.e., the bucket was on display, but its contents were still hidden).

### Step 4: Make the Bucket Objects Public

To resolve the '403 Forbidden' error, I navigated to the 'Objects' tab of my bucket, selected my index file and assets folder, clicked on 'Actions', and then clicked on 'Make public using ACL'.

Now, I refreshed the web page displaying the error and verified that the error was resolved.

A screenshot of my successfully hosted static website on S3 is shown below.

![Image](https://github.com/sumeet15n/host-a-website-on-S3/blob/master/Screenshots/SS5.JPG)

### Step 5: Delete Resources

Finally, I deleted all the created resources after completing this project to avoid any further charges on AWS.

---

## Project Reflection

This project took me approximately 30-45 minutes to complete. The most challenging part was to troubleshoot the '403 Forbidden' error, and the most rewarding part was to see the website being successfully hosted.

Big thanks to NextWork (https://www.nextwork.org/) for this project! I highly recommend this platform to anyone who wants to learn DevOps concepts and complete more projects like this one. The project guides on the platform are detailed, along with a walkthrough YouTube video for each project. Happy learning!