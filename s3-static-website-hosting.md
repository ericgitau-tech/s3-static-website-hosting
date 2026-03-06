<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Eric Gitau  
**Email:** gitaueric09@gmail.com

---

![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project, I demonstrate how to use Amazon S3 to host a static website. The goal of this project is to learn how AWS cloud services can be used to store objects in the cloud and host websites in a scalable and reliable way.

### Tools and concepts

Key services and concepts I learned: Amazon S3, buckets, static website hosting, bucket endpoints, Block Public Access, ACLs, object permissions, and fixing 403 errors

### Time, challenges, and wins

It took me about 30 minutes to complete the project, including learning new concepts like Block Public Access and ACLs

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will be creating and s3 bucket because this is where I will be storing my things.

### How long it took to create the bucket

Creating an S3 bucket took me about five minutes. Along the way, I had to learn a few new concepts such as Block Public Access and ACLs. Once I understood those, I was able to create buckets much faster in the future.

### Region selection

The Region I picked for my S3 bucket was eu-west-1 because it is the one closest to me. It is the best practice to choose a region closest to m you so that it can lower the time to retrive your things (aka latency).

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no any  other person can own that name of the bucket.

![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will upload the website files to the S3 bucket. This is important because without files, there’s no website our bucket is still empty! Let’s me add the files so we actually have a site to host.

### Files I uploaded

I uploaded two files to my S3 bucket - an index.html file(this determines the structure i.e what goes inside my website)  and a folder containing images and other assets

### How the files work together

Both files are necessary for this project because index.html is the main webpage, while the assets folder holds images/styles it uses. Without both, the site won’t display correctly.

![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will make my website available to the world. This is called static website hosting, and it is important because my website files will remain just files unless I enable this feature.

By turning on static website hosting in Amazon S3, my files (HTML, CSS, and images) can be served as an actual website instead of simply being stored as objects in a bucket.

### Understanding website hosting

Website hosting means placing my website files on a web server, which is a specialized computer designed to store, process, and deliver website content so that it can be viewed as a webpage by anyone on the internet.


### How I enabled website hosting

To enable website hosting for my bucket in Amazon S3, I went to the Properties tab, enabled static website hosting, and set "index.html" as the index document this is the main file that will be hosted and displayed when users visit the website.

### Access Control Lists (ACLs)

An ACL (Access Control List) is a way to configure permission settings inside an Amazon S3 bucket. I enabled ACLs so that I can control access to my website files later.
There was a popup mentioning that Amazon Web Services recommends disabling ACLs. However, I decided to keep them enabled so I can learn how ACLs work and compare them with bucket policies.


![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is a unique web address Amazon S3 gives your bucket after enabling static hosting, letting users access your website through a browser

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I received a 403 Forbidden – Access Denied error. This happened because objects in Amazon S3 are private by default. Even if “Block all public access” is turned off at the bucket level, the individual website files (objects) remain private. Their permissions must be configured separately to allow public read access so that visitors can view the content of my website.

![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will go into the files I uploaded to my bucket and make them public. This is necessary because it allows users to access and view the content of my website. Once I update the object permissions in Amazon S3 to allow public access, my website will officially be live.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I made the uploaded files public in the S3 bucket. This allowed the website content to be accessible through the endpoint URL

![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

In this project extension, I will use bucket policies to control access to my bucket files. I am doing this to prevent users from deleting the objects stored inside my bucket. By configuring a bucket policy in Amazon S3, I can define specific permissions such as allowing public read access while explicitly denying delete actions to better protect my website content.

### Understanding bucket policies

An alternative to ACLs is bucket policies, which are rules that define who is allowed or not allowed to perform specific actions on a bucket and its objects. The benefit of using bucket policies is that they provide more detailed and flexible control over permissions, allowing you to manage actions such as viewing, uploading, or deleting files. In Amazon S3, bucket policies are generally preferred for broader access control, while ACLs are mainly useful for managing public access at the individual object level.


![Image](http://learn.nextwork.org/inspired_purple_vibrant_plum/uploads/aws-host-a-website-on-s3_sm2sm2sm)

### What my bucket policy does

Our bucket policy denies everyone from deleting the index.html file in the bucket. I tested this by attempting to delete the file and received a Permission Denied error. This confirms that the bucket policy in Amazon S3 is working correctly—it successfully prevented the deletion of the object we wanted to protect.

---

---
