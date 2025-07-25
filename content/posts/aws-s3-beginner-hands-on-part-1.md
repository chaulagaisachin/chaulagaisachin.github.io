---
title: "Beginner friendly Hand-on Project on AWS S3 — Part 1"
date: 2024-03-01T14:33:02+11:00
draft: false
toc: false
images:
tags:
  - AWS
  - S3
  - Cloud
  - Storage
  - Object Storage
  - Beginner
  - AWSs3
  - AWSBucket
  - AWSObject
  - AWSObjectStorage
  - AWSStorage
  - AWSBeginner
  - s3policy3
categories:
  - Cloud
  - AWS
  - S3
author: "Sachin Chaulagai"
---

![intro](https://miro.medium.com/v2/resize:fit:828/format:webp/1*7rlT1QToYMlKF5xsTOBHiw.jpeg)

I want to help beginner gain some confident on their journey in cloud and tech. I will be posting tutorials and lessons on cloud tech and security such that its more understandable and have not burden but fun and easy to comprehend. Let’s start with a service provided by AWS, called Amazon S3.

You ever heard about S3? No! Ever used Google Drive to store your files online? Yes! It’s a primary example of how object storage works.

There are tons of ways to store a file in a cloud system. Object storage is one of that way. Don’t panic if you don’t understand what an “Object Storage” is. It's just a techy way of saying that the file will be treated as a distinct unit, that's all you need to know for now.

Okay, so it stores files distinctly. Good. Now you need to know about what a bucket is. What bucket? Don’t push your nerves. Think it of as a container where you store your file. It makes the file more manageable.

**Features**:

* Of course, you can save file in it. Duh. But it’s very fast. In tech world, it has a low latency and high throughput. (Be familiar with these terms, open the dictionary)
* Its available up to 99.999999999% of the time in a whole year. Mean, it durable.
* Security, you can use policies to manage the access to the files.
* Host a static web content through AWS S3.
……….and there any many more features, you will know when you work with it a bit. Let's jump to a simple tutorial.

**Overview**:

![archi](https://miro.medium.com/v2/resize:fit:828/format:webp/1*wWmRrFhVUmmolr4jZpB9qA.png)

* This is what we are going to do. Create a bucket, upload some files in it, and the files public to share with others. Break it down, make it simple.

**Creating bucket in AWS**:

* Go to https://aws.amazon.com/ sign up if you have never had an account. Explore but don’t go too deep into various services, it kind of feels overwhelming.
Search and select S3 services on the panel.

![1](https://miro.medium.com/v2/resize:fit:828/format:webp/1*XcfUk7zlZQ9JbBui3LTv2g.png)

![2](https://miro.medium.com/v2/resize:fit:828/format:webp/1*F6f38xXphlHwi-wl9U6aDA.png)


* Select Create bucket and you’ll see a portal to configure your bucket. Make sure you have a unique name for your bucket.

![3](https://miro.medium.com/v2/resize:fit:828/format:webp/1*PI9PG0cT-vDzF2Thciy5nA.png)

* Let any other configuration be as it is. Scroll to the end of the page. Select Create Bucket. You’ll see the following page.

![4](https://miro.medium.com/v2/resize:fit:828/format:webp/1*1Pob7Pj2u89QhSl-5zVk8Q.png)

* Let’s upload files inside your newly created bucket.

* Select your newly created bucket and see following page. This is where you can configure everything related to your bucket.

![5](https://miro.medium.com/v2/resize:fit:828/format:webp/1*I-5As2y20N9zqxfG7AAm-g.png)

* Select Upload and now you can see different options to Add files and Add Folder. For now, we’ll just add a single file.

![5](https://miro.medium.com/v2/resize:fit:828/format:webp/1*whdeo1v5Q-9ed4aYCwDUGg.png)

* Select your file and upload. I uploaded a file name “friendly-cloud-rat.jpg”.

![6](https://miro.medium.com/v2/resize:fit:828/format:webp/1*kzBzSkjR8P17tyOAJQA-tg.png)

* Upload succeeded.

![7](https://miro.medium.com/v2/resize:fit:828/format:webp/1*jeWq7uyu4nNCVj-4YxCvEg.png)

* You will be able to list all your file inside your bucket. Select the file and “Copy URL” of the file. This URL redirects you to your file inside S3 bucket.
**Extra stuff**: AWS Route53 maps S3 object with a URL

![8](https://miro.medium.com/v2/resize:fit:828/format:webp/1*DhoqWEuPTaL6WkviyLfjlg.png)

* Open another tab and enter your URL.

![9](https://miro.medium.com/v2/resize:fit:828/format:webp/1*CUKPLZkoq12PYIInRwJVyA.png)

* DAMMMMMMMMMnnnnnnnnnnnnn. Why is it not working? If you are really reading this, comment your thoughts on why didn’t this work? This is just a checkpoint to make sure you are devoted to this tutorial, not just skimming and making yourself feel that you know stuff. I used to do that, that’s not good. “Apply yourself” that’s what I am doing. *a lil pep talk

![10](https://miro.medium.com/v2/resize:fit:828/format:webp/1*5H8TJOBxn44AqMRQbYxvoQ.png)

* By default, AWS S3 bucket “Block all public access” is turned on. Go to Permissions in your bucket configuration.

![11](https://miro.medium.com/v2/resize:fit:828/format:webp/1*8wBCut3Dxu59Otf4T8xKnw.png)

* Select edit. Read this all if you want, but no worries take it easy.

![12](https://miro.medium.com/v2/resize:fit:828/format:webp/1*3ILk4js7OHIqgUN3KFn5lw.png)

* Turn it all off. Select Save Changes

![13](https://miro.medium.com/v2/resize:fit:828/format:webp/1*Bggi3uxQ3wyHo0S7YLvYaA.png)

* Confirm bro.

![14](https://miro.medium.com/v2/resize:fit:828/format:webp/1*PZn_Gza3pqm9FXoMNe-0PQ.png)

* TRY AGAIN. Copy Object URL. Go to the link.

![15](https://miro.medium.com/v2/resize:fit:828/format:webp/1*NEx_MimZ-Jbg1QClr_mkLQ.png)

* ughhhhhhhhhhhhhhh. Don’t worry. It's a security stuff, S3 is actually public. However, to access the files inside it, an explicit policy needs to be implemented.
* Go to Permissions tab for your bucket. Scroll down to Bucket Policy and select Edit.

![16](https://miro.medium.com/v2/resize:fit:828/format:webp/1*NMI6YiGXTwUxiWfHv4gdcA.png)

* It might get boring here, but this is what it takes to build better stuff.  
For now just copy the JSON policy and paste it. Don’t burden too much on any stuff, continue tomorrow if its too much. Take it EASSyyy.


![17](https://miro.medium.com/v2/resize:fit:828/format:webp/1*jbNVWg2nGI0RBL7XVAKz9Q.png)

* Paste the below policy to bucket policy and save it.

`{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::myunique-aws-s3-bucket/*"
        }
    ]
}`


![18](https://miro.medium.com/v2/resize:fit:828/format:webp/1*cJ7sPYaaj6NxLLFSvP0tDQ.png)

* See something different. Copy the object URL and try again.

![19](https://miro.medium.com/v2/resize:fit:828/format:webp/1*TpDnCXmVbuprlKWyhGbz2w.png)

* We made it. NOICEEEEEE  

If you read it till here, thank you and thank yourself for your dedication. If you didn’t understand this, comeback tomorrow and read it again. Comment any questions, there are a lot of student and people even professional who are afraid and nervous about asking question. Don’t worry about anybody else, just comment. Public comments will encourage others to normalize asking question. I’ll be happy to help. Peace.
