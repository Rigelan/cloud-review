# cloud-review
general public training camp notes with random cloud tips for summer 

# Docker to cloud

Template to run in cloud
[ECS-UPGRADE][<https://in4it/ecs-upgrade>]

```
docker run -it -e AWS_ACCESS_KEY_ID=... -e AWS_SECRET_ACCESS_KEY=... -e AWS_REGION=... -e ECS_ASG=your-asg -e ECS_CLUSTER=yourcluster in4it/ecs-upgrade
```

## Training code camp example for summer

Part 1  Establish a S3 object bucket to host public static web content
Note: S3 previously defaulted to world accessible.  

Due to the care required when providing access to S3 object storage and 

likelihood of abuse of too open settings, AWS sets S3 to private by default.   

Please research, test and configure what you need this bucket to do with a 
single test file before putting valuable data prior to having your security ready

See following link for hints on part 2 below
https://www.agiratech.com/hosting-a-simple-static-website-on-aws-s3/ (edited) 
9:41

Part 2  Quick steps to provide bucket as a web page

  1. Create an S3 bucket
  2. Configuring it as a Website  (carefully start with test content)
  3. Unblocking public access settings
  4. Adding a bucket policy
  5. Uploading static web application
  6. Testing the Website

9:43
Part 3  Testing integration with Hosted Dynamic web site

  1. Provide referral page to public site
  2. Test latency using public site directly
  3. Test latency using S3 referral page to public site directly
  4. If within approved limits proceed to Part 4

### Supplement

Rather than Part 2, following AWS' example for using a custom domain.   You will still have to (part 3) re-work it to forward to www.yoursite.com, but it at least pushing unblocking the public access to later in the process.https://docs.aws.amazon.com/AmazonS3/latest/dev/website-hosting-custom-domain-walkthrough.htmlTopics

    Before You Begin
    Step 1: Register a Domain
    Step 2: Create Two Buckets
    Step 3: Configure Your Root Domain Bucket for Website Hosting
    Step 3: Configure Your Subdomain Bucket for Website Redirect
    Step 4: Configure Logging for Website Traffic
    Step 5: Upload Index and Website Content
    Step 6: Edit Block Public Access Settings
    Step 7: Attach a Bucket Policy
    Step 8: Test Your Domain Endpoint
    Step 9: Add Alias Records for Your Domain and Subdomain
    Step 10: Test the Website

docs.aws.amazon.comdocs.aws.amazon.com
Walk through a code example of how to set up a static website using a custom domain.
