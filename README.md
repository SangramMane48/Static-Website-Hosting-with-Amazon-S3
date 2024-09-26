# Static-Website-Hosting-with-Amazon-S3

 # Step 1: Create an S3 Bucket
  1.Log in to AWS Management Console: Go to the AWS Management Console and log in with your credentials.

  2.Navigate to S3: In the AWS Management Console, find and select S3 from the services menu.

  3.Create a New Bucket:

- Click on the "Create bucket" button.
- Bucket Name: Enter a unique bucket name (e.g., my-static-website-bucket).
- Region: Choose a region (e.g., us-east-1).
- Block Public Access Settings: Uncheck "Block all public access" to allow public access to your website.
- Review the options and click "Create bucket".


# Step 2: Configure Bucket for Static Website Hosting

1.Enable Static Website Hosting:

- Click on your newly created bucket.
- Navigate to the "Properties" tab.
- Scroll down to the "Static website hosting" section and click "Edit".
- Select "Enable".
- Index Document: Enter index.html.

2.Set Bucket Policy for Public Access: To allow public access to your static website:

- Go to the "Permissions" tab of your bucket.
- Click on "Bucket Policy".
- Enter the following policy, replacing my-static-website-bucket with your actual bucket name:
- Error Document: Optionally enter error.html.
Click "Save changes".
```
 {
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-static-website-bucket/*"
    }
  ]
}
```
- Click "Save" to apply the policy.

# Step 3: Prepare Your Website Files

index.html

- Create an index.html file as your main web page:

  ```
   <!DOCTYPE html>
   <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Static Website</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Welcome to My Static Website</h1>
    <p>This is a simple static website hosted on Amazon S3.</p>
    <button onclick="showAlert()">Click Me!</button>
    <script src="script.js"></script>
  </body>
  </html>

  ```
styles.css

- Create a styles.css file to style your website:

```
body {
    font-family: Arial, sans-serif;
    margin: 20px;
    background-color: #f4f4f4;
}

h1 {
    color: #333;
}

button {
    padding: 10px 15px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;  /* Darker shade on hover */
}
```
script.js

- Create a script.js file for your website's interactive functionality:
```
function showAlert() {
    alert("Hello! Welcome to my static website hosted on Amazon S3.");
}
```
# Step 4: Upload Website Files to S3

1.Upload Files:

- Go back to your S3 bucket.
- Click on the "Upload" button.
- Drag and drop your index.html, styles.css, and script.js files into the upload window.
- Click "Upload" to start the upload process.

# Step 5: Access Your Static Website

1.Get the S3 Website Endpoint:

- Navigate back to the "Properties" tab of your S3 bucket.
- In the "Static website hosting" section, you will see the Endpoint URL.
- Copy this URL.
  
2.Open Your Website: Paste the URL into your web browser. You should see your static website live!

# Step 6: GitHub Repository Setup

1.Create a GitHub Repository:

- Go to GitHub and log in.
- Click on the "+" icon in the top right corner and select "New repository".
- Name your repository static-website-s3.
- Add a description: "A guide for hosting a static website using Amazon S3."
- Choose the repository visibility (public or private).
- Initialize the repository with a README file.

2.Clone the Repository: Open your terminal and run the following commands to clone your repository:

```
git clone https://github.com/yourusername/static-website-s3.git
cd static-website-s3
```
Replace yourusername with your actual GitHub username

3.Add Your Files: Copy your index.html, styles.css, and script.js files into the cloned repository directory.

4.Create a README.md File: In your repository, create a README.md file that contains the instructions and information about your static website. Here’s a template for your README.md:
```
# Static Website Hosting with Amazon S3

This repository provides a comprehensive guide on how to host a static website using Amazon S3.

## Overview

Amazon S3 offers a scalable and cost-effective solution for serving static content such as HTML, CSS, JavaScript, images, and other web assets. This guide covers the steps to set up an S3 bucket for static website hosting, configure permissions, and upload your website files.

## Repository Structure
```
static-website-s3/ │ ├── index.html ├── styles.css ├── script.js └── README.md
```

## Steps to Host a Static Website

1. **Create an S3 Bucket**
2. **Configure Bucket for Static Website Hosting**
3. **Prepare Your Website Files**
4. **Upload Website Files to S3**
5. **Access Your Static Website**

## Accessing the Website

After following the instructions, you can access your website at the S3 website endpoint.
```
5.Commit and Push Your Changes: After adding your files and updating the README, run the following commands to commit and push your changes to GitHub:
```
git add .
git commit -m "Initial commit: Added static website files and README."
git push origin main
```
Conclusion:
You have successfully created a GitHub repository that serves as a guide for hosting a static website using Amazon S3. By following the steps outlined in this repository, you can easily set up and deploy your own static website on AWS.
