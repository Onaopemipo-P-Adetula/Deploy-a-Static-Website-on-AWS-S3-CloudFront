#  Deploy a Static Website on AWS using S3 and CloudFront

This project demonstrates how to host a static website using Amazon S3 and serve it globally using Amazon CloudFront, a Content Delivery Network (CDN).

## Diagram
![deploy static webite on aws using s3 and cloudfront](https://github.com/user-attachments/assets/742f08d4-6da3-4014-9ded-c1fdb5b8680b)




## Features
- Static website hosting using AWS S3
- Global content delivery via CloudFront
- Optional: HTTPS with SSL, custom domain setup



##  Tools Used
- AWS S3
- AWS CloudFront
- (Optional: Route 53  + custom domain)



##  Project Files
- `index.html`: Main homepage
- (Optional) `style.css`, images, etc.



##  Steps to Reproduce

### 1. Prepare Website Files
- Create a basic `index.html` (or use a free HTML template).
- Put the HTML code into a file called index.html and save it in a named folder.
- Create a folder called css, and save the style code in a file named style.css inside that folder.
- Put your images (e.g., logo, hero, pastor photo) into the images folder

---

### 2. Create an S3 Bucket
1. Go to [S3 Console](https://s3.console.aws.amazon.com/s3/home)
2. Click **Create bucket**
   - Bucket name must be globally unique
   - **Uncheck "Block all public access"**
   - Enable **Static website hosting** in the Properties tab
   - Set `index.html` as the default root document

---

### 3. Upload Website Files to S3
- Upload all files (`index.html`, images, etc.) to the bucket
- Make them **public**
- Optional: Add bucket policy to make all objects public (see below)

---

### 4. Create a CloudFront Distribution
1. Go to [CloudFront Console](https://console.aws.amazon.com/cloudfront/)
2. Click **Create Distribution**
3. Under **Origin domain**, choose your S3 bucket (use website endpoint)
4. Origin Access: Choose "Public" if your S3 content is public
5. Default Cache Behavior: Leave as-is for now
6. Set Viewer Protocol Policy to Redirect HTTP to HTTPS
7. Price class: Choose "Only North America and Europe" if you want to save costs
8. Alternate domain name (CNAME): Add if you want to use your own domain
9. SSL certificate: Choose "Default CloudFront certificate" for now (for HTTPS)
10.  Click **Create distribution**

---

### 5. (Optional) Set Up Custom Domain + HTTPS
- Use Route 53 to register/set up your domain
- Request an SSL certificate 
- Attach it to CloudFront

---

