---
title: "AWS Global Infrastructure"
date: 2024-09-08
description: "A guide to understanding AWS Global Infrastructure: regions, availability zones, and edge locations."
image: ""
author: "Sachin Chaulagai"
tags: [AWS, Aws Certification, Infrastructure, Cache, Interview]
---

## AWS Global Infrastructure

This blog will guide you on the right path to understanding cloud infrastructure. By the end, you’ll have a clear understanding of how AWS Global Infrastructure operates to deliver its services efficiently.

As discussed in my previous blog on virtualization, we understand that ultimately, it’s all about managing key computing resources like CPU, RAM, networking, and GPU. But how does AWS manage such a vast infrastructure?

To answer that, we first need to understand the three major components of their architecture.

- AWS Regions
- Availability Zone
- Edge Location

### AWS Regions

AWS Region: These are geographical location where a large datacenter is located. Region may have more than one availability zone that manages their own resources. We’ll come back to AZ. As for today, there are about 34 launched AWS regions all over the world. Why so many regions? Having data centers in multiple regions allows AWS to offer faster services, reduce latency (the time it takes for data to travel), and improve reliability. It also helps companies meet local data privacy regulations by storing data in certain countries.

### Availability Zones

Availability Zones: AZs are the physical where the datacenters are hosted. Huh, isn’t the AWS region same? No. A region is a large geographic area containing multiple availability zones (AZs), while an AZ is a distinct, isolated data center within a region. Refer to the picture above & give yourself sometime to think about it. These AZs are close to each other but are separate so that if something happens to one, it won’t affect the others. AWS AZs give you the building blocks (compute, storage, networking, etc.) to run and manage your applications with high reliability and performance.

### Edge Location

Edge Location: An Edge Location in AWS is a server located closer to users to make data and services faster. Instead of going all the way to a main data center (such as AZs), requests like loading a website or streaming a video are handled at these nearby Edge Locations. This reduces the time (latency) it takes to get data, resulting in faster and smoother user experiences. Edge Locations are key to services like Amazon CloudFront, which delivers content quickly around the world.

These three components of AWS’s global infrastructure enhance the speed and efficiency of service delivery. I’m here to answer any questions you might have and welcome any feedback you’d like to share.

My goal is to keep the content bite-sized for easier understanding. I’ll continue updating and sharing my expertise through various channels. Thank you!
