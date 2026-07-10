Project Overview
The cloud is perfect for hosting static websites that only include HTML, CSS, and JavaScript files that require no server-side processing. The whole project has two major intentions to implement:

Hosting a static website on S3 and
Accessing the cached website pages using CloudFront content delivery network (CDN) service. Recall that CloudFront offers low latency and high transfer speeds during website rendering.
Note that Static website hosting essentially requires a public bucket, whereas the CloudFront can work with public and private buckets.

Important note about S3 and CloudFront

Traditional S3 static website hosting requires the bucket objects to be publicly accessible when you use the S3 website endpoint.
However, CloudFront can be configured to serve content from a private S3 bucket using Origin Access Control (OAC) or Origin Access Identity (OAI). Using CloudFront with OAC/OAI is the recommended, more secure approach because you can keep your bucket private while still delivering content via the CDN.
Be aware of S3 Block Public Access settings: they can prevent public website hosting. If you plan to use the S3 website endpoint, you may need to adjust those settings or use CloudFront + OAC instead.
What you will do in this project

Create an S3 bucket and upload the website files.
Configure the bucket for static website hosting (or configure CloudFront to use the bucket as a private origin with OAC/OAI).
Secure access with appropriate bucket policies or CloudFront origins.
Create a CloudFront distribution to speed up delivery and optionally configure caching, TTL, and invalidation.
Access the website through the CloudFront endpoint (or your custom domain pointing to CloudFront).
