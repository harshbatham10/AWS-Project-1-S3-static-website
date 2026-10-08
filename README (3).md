# 🌐 Static Website Hosting on Amazon S3

A simple static website hosted on **Amazon S3** using the Static Website Hosting feature, created as part of my AWS Project Assignment.

**Live URL:** http://harsh-s3-staticwebsite-2026.s3-website-us-east-1.amazonaws.com

> Note: S3 website endpoints use HTTP only. The link may stop working if the bucket is deleted or made private.

---

## 📌 Project Overview

This project shows how to host a static website (HTML + CSS) without any server, using only Amazon S3.

| Item | Details |
|------|---------|
| Service used | Amazon S3 |
| Bucket name | `harsh-s3-staticwebsite-2026` |
| Region | US East (N. Virginia) `us-east-1` |
| Hosting type | Static website hosting (bucket hosting) |
| Index document | `index.html` |

---

## 📁 Project Structure

```
.
├── index.html        # Main web page
├── style.css         # Styling for the page
├── screenshots/      # Console and output screenshots
└── README.md
```

---

## 🛠️ Steps to Deploy

### 1. Create an S3 bucket
- Open **S3 → Create bucket**.
- Enter a globally unique name (`harsh-s3-staticwebsite-2026`) and choose the `us-east-1` region.

### 2. Upload website files
- Open the bucket → **Objects → Upload**.
- Upload `index.html` and `style.css`.

### 3. Enable static website hosting
- Go to **Properties → Static website hosting → Edit**.
- Select **Enable** and **Host a static website**.
- Set **Index document** to `index.html` and save.

### 4. Allow public read access
- Go to **Permissions → Block public access** and turn off the block settings for this bucket.
- Enable ACLs (**Bucket owner preferred**), then select the files and choose **Actions → Make public using ACL**.
- (Alternative, recommended) Add a bucket policy that allows `s3:GetObject` for the bucket's objects.

### 5. Open the website
- Go to **Properties → Static website hosting** and copy the **Bucket website endpoint**.
- Open it in a browser.

---

## 🔒 Example Bucket Policy (optional alternative to ACLs)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::harsh-s3-staticwebsite-2026/*"
    }
  ]
}
```

---

## 📸 Screenshots

| Step | Screenshot |
|------|-----------|
| Bucket created | 
| Files uploaded | 
| Static website hosting enabled |
| Make objects public | 
| Website endpoint | 
| Live website |

--- 

## Create Bucket 

![image alt](https://github.com/harshbatham10/AWS-Project-1-S3-static-website/blob/761b4386bd4ce4a43a88a1d88566afe28a98c91b/Screenshot%20(40).png)

## ☁️ AWS Services Used

- Amazon S3

---

## 📚 What I Learned

- How to create and configure an S3 bucket
- How S3 static website hosting works
- How Block Public Access, ACLs and bucket policies control access
- How to access a site through the S3 website endpoint

---

## 🚀 Future Improvements

- Add **Amazon CloudFront** for HTTPS and faster global delivery
- Use a custom domain with **Amazon Route 53**
- Automate deployment with the AWS CLI or GitHub Actions

---

## 👤 Author

**Harsh Batham**

---

## 📄 License

This project is for learning purposes.
