How to Host a Static Website on AWS S3 Bucket


Are you looking to host a static website in a simple and cost-effective way? AWS S3 (Simple Storage Service) offers a reliable and scalable solution. In this post, I'll guide you through the steps to host your static website on an S3 bucket.
Step 1: In this step we ensure that we have all files (index.html, css, javaScript etc) or folder ready of our website  
Step 2: Create an S3 Bucket
Login to AWS Management Console: Start by logging into your AWS account.
Navigate to S3: In the AWS services menu, find and select 'S3'.

Create a Bucket: Click on the ‘Create bucket’ button. Choose a unique bucket name and select your preferred AWS region mine mumbai region.


Select the ACL enabled Option 

Set Permissions: Make sure to set the bucket's permissions so that it can serve content publicly.

After that Click on Create Bucket Option.
Step 3: In this step we upload our website files
Access Your Bucket: Once the bucket is created, open it and click on upload files option and Drag and Drop All files or folders of our website.
After that click on upload Option.




Step 4 - After uploading all the files we need to give permission to Access publicly all files because a static website requires public access, you need to make the objects public.
Select all the files & folder and click on Actions and make public acl enable and click on Make Public Option.



Step 5 - In this Step we will set the bucket policy for Allow public access so gon on the Permission tab in our bucket and scroll down we will see Bucket Policy option click on Edit.  After that Enter the following bucket policy, replacing our-bucket-name with our actual bucket name:	
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::our-bucket-name/*"
    }
  ]
}

And click on Save Changes . 
Step 6 - This is final Step In this step we need to configure Bucket For Static Website 
So Click on Properties Tab and Scroll down and find the Static Website hosting section and click on Edit. 

And select Enable for static website hosting.Set Index document as index.html (or any other main HTML file you want to display).If you have a custom error page, specify it (e.g., error.html).

And click on Save the changes. 
After click on save changes we get the url or our website capy that url and open in Browser. 



🎉😊 Congratulations! Your website is now live on AWS S3.



