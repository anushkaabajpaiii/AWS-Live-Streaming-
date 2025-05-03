# AWS-Live-Streaming-
A scalable, reliable, and low-latency live video streaming platform built using Amazon Web Services (AWS). This project enables real-time broadcasting and playback of live video using AWS Media Services, such as AWS Elemental MediaLive, MediaPackage, and Amazon CloudFront.

📌 Features
🔴 Live video ingestion via RTMP

📦 Real-time video packaging using AWS MediaPackage

🌍 Global content delivery with low latency via Amazon CloudFront

🔐 Secure playback with signed URLs (optional)

📱 Cross-device and adaptive bitrate streaming (HLS, DASH)

🧩 Easily extendable for recording, analytics, or user interactivity

🛠️ Tech Stack
AWS MediaLive – Live video encoding

AWS MediaPackage – Video packaging for multiple streaming formats

Amazon CloudFront – CDN for scalable delivery

Amazon S3 – Static website hosting (optional)

IAM Roles & Policies – Secure service communication

CloudFormation / Terraform (optional) – Infrastructure as Code

📷 Architecture
css
Copy
Edit
[RTMP Source (OBS)] → [MediaLive] → [MediaPackage] → [CloudFront] → [Viewer]
🚀 Getting Started
1. Prerequisites
AWS account with sufficient permissions

OBS Studio or other RTMP-compatible broadcaster

Domain name (optional, for custom player or signed URLs)

2. AWS Setup Steps
Create an Input in AWS MediaLive (RTMP push)

Create a Channel in MediaLive and attach the input

Configure MediaPackage as the channel output

Set up a CloudFront Distribution pointing to the MediaPackage endpoint

Use OBS to push a stream to the MediaLive RTMP endpoint

Access the Playback URL (HLS/DASH) via CloudFront

3. OBS Configuration
Stream Type: Custom

Server: rtmp://<MediaLive-RTMP-endpoint>

Stream Key: <Channel stream key>

📄 Example Playback
You can embed the CloudFront-delivered HLS playback in a custom web app using HTML5 players like:

html
Copy
Edit
<video controls autoplay width="100%">
  <source src="https://your-cloudfront-url/hls/index.m3u8" type="application/x-mpegURL">
</video>
Or use libraries like Video.js or Shaka Player for advanced playback options.

🔐 Security (Optional)
Enable Signed URLs in CloudFront for controlled access

Configure CORS policies in MediaPackage

Use WAF and Shield for DDoS protection

📦 Deployment Automation (Optional)
Automate provisioning using:

AWS CloudFormation

Terraform (with aws_media_live, aws_media_package_channel, etc.)

AWS CDK (for TypeScript or Python users)

📚 Resources
AWS Live Streaming on AWS

MediaLive Docs

MediaPackage Docs

OBS Setup Guide

