<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)

**Author:** Carroll Robin R  
**Email:** carrollrobin94@gmail.com

---

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Introducing Today's Project!

### Project overview

In this project, I will be creating a static website which will be hosted through AWS service called the S3 

### Tools and concepts

Services I used mainly involved the AWS S3. Key concepts I learnt include setting up an S3 bucket with ACL,bucket versioning and Block public access, what is ACL and Bucket policies and how do they differ, Activating ACL to make the objects public, Enabling of static website hosting to display the webpage created to Everyone and writing Bucket policy to prevent deletion of index.html by anyone.

### Time, challenges, and wins

This project took me approximately hour and a half. The most challenging part was after fixing the 403 forbidden error, only the html components of the webpage were visible, the other assets such as images,css and javascripts weren't working to bring the website to life. The mistake I made was that instead of uploading the sub folders that were inside the unzipped folder, I instead  uploaded the unzippled folder directly into the bucket, thus the webpage assets weren't able to communicate properly to be displayed, sometime later, I realised the mistake, rectified it and the website worked perfectly

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will log onto my AWS console and open up S3, after opening up the S3 console, I will upload the relevant files to display a static website on it.

### How long it took to create the bucket

Creating an S3 bucket didn't take much time as AWS had a simple console of buttons which we only had to click on to Enable or Disable a particular feature such as turning on the ACL under Object Ownership or disabling Block Public Access so that the website can be seen by everyone

### Region selection

The Region I picked for my S3 bucket was Asia Pacific because I believed I had a less chance of conflicting with any other AWS account bucket names and latency would be lower

### Understanding bucket name uniqueness

S3 bucket names must be globally unique. This means that the name I use for the bucket can't be used by others no matter where they are in the world because all AWS users share the same namespace.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I am going to upload an HTML file to set up the website and a zip file with images to the S3 bucket

### Files I uploaded

I uploaded two files to my S3 bucket - they were index.html which contained the structure or blueprint for the website and a folder called "Everyone should be in a job they love" which contained relevant objects such as images and more to bring the website to life.

### How the files work together

Both files are necessary for this project as the html file lays down the blueprint which tells the bucket, where to place the images and text on the webpage.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I will be configuring my bucket in S3 to be able to do static website hosting and visit a live link of the website that I have just created.

### Understanding website hosting

Website hosting means a user from the internet can access the webpage that I have created as it's stored on a web server, making the page accessible globally. 

### How I enabled website hosting

To enable website hosting with my S3 bucket, I clicked on my bucket, at the top below the bucket's name, I clicked on the option called Properties and at the very end of the page, was the option to enable or disable static website hosting.

### Access Control Lists (ACLs)

An ACL is a access control system which predates the IAM. It grants basic read or write permissions to other AWS accounts. It's weakness is that it's a security risk as it can't stop a user from writing malicious code since it has given the user, permission to do read and write operations to the website while bucket policies can prevent these by allowing specific allowance but it's complex than ACL. I have enabled ACL for this project to be able to access each object individually.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is a link that users can access to visit the website

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw the 403 forbidden error message. The reason for this error is that the objects in the Bucket are set to "private" by default for data safety reasons. Now we have to change it to public to fix the error.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_22ce4daf)

## Success!

### What I did in this step

In this step, I will make the website files in my S3 bucket change from private to public so that the files are accessible and will be able to be displayed on the webpage.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I had to go to the S3 console and select a option called Make public with ACL,  this can be done only after selecting the objects that need to be made public. 

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension I'm about to implement a Bucket policy,  I'm doing this so that public users won't be able to delete or insert malicious code into my index.html file.

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are written on JSON. The benefit of using bucket policies is that they allow for greater control over who does what to the objects and if in case, it becomes suspicious, the modification will be denied while ACLs are useful for basic read and write permissions and can be setup by clicking on Checkboxes but their major flaw is the lack of control over who does what to the objects in S3.

![Image](https://nextwork.ai/lively_orange_innocent_peacock/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_sm2sm2sm)

### What my bucket policy does

My bucket policy was to prevent the deletion of index.html file by anybody including myself. I tested this by implementing the required code to make this happen and saw that when I tried to delete the index.html file, an error messaged popped up saying that it failed to delete the object because the access for it was denied.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)*
