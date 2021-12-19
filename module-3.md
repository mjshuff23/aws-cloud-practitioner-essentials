# Module 3 - Global Infrastructure and Reliability

## Learning Objectives

- Summarize the benefits of the AWS Global Infrastructure
- Describe the basic concept of Availability Zones
- Describe the benefits of Amazon CloudFront and edge locations
- Compare different methods for provisioning AWS services

## Introduction

To understand the AWS global infrastructure, consider a coffee shop. If an event such as a parade, flood, or power outage impacts one location, customers can still get their coffee by visiting a different location only a few blocks away.

This is similar to how the AWS global infrastructure works

## AWS Global Infrastructure

If you run your own data center, you have to decide what to do if and when disaster happens to your data center (server).  With AWS global infrastructure, you don't need to worry about that because AWS redundantly stores your data among many of it's data centers.

- AWS builds it's data centers in large groups called **regions** in areas where the most traffic is expected, like Tokyo, Paris, Virginia, ...
- AWS regions are connected through a high speed fiber network.
- You choose the region you want to run out of
- No data from one region will be shared with another region without **explicit consent** from you
  - This is called **regional data sovereignty**
- There are four business factors that go into choosing a region:
  1. **Compliance** - You must look at your compliance requirements, but most businesses are not governed by such strict regulations
  2. **Proximity** - How close you are to your customer base is an important factor
     - Proximity will determine the **latency** of communication, which is the time it takes for data to be sent and received
  3. **Feature Availability** - Sometimes the closest region may not have all of the AWS features you want
  4. **Pricing** - Even when the hardware is equal, some locations are more expensive to operate in, such as Brazil

### Availability Zones

- AWS has many **data centers**
- A large group of data centers is known as a **Region**
- A data center or small group of data centers is known as an **Availability Zone**
  - This means that a Region is a group of Availability Zones
  - Availability Zones are separated from each other inside their Region in order to avoid massive scale failure
  - Availability Zones can be as far as 10 miles apart and keep single digit latency communication between other Availability Zones in the Region, allowing your business to stay up and running when failures occur
  - It is suggested to run your apps across at least two Availability Zones in a Region, which means redundantly deploying it in two AZs
- Regionally Scoped AWS services have a high availability automatically

### Edge Locations

- When selecting a Region, a primary concern is proximity to your customers, but what if your customers are all over the world?
- Caching data in locations that are close to customers is the primary idea behind **Content Delivery Networks (CDN)**
- **Amazon CloudFront** is Amazon's CDN
  - Helps deliver data, video, applications, and APIs to customers with low latency and high transfer speeds
  - Utilizes **Edge Locations** from around the world to help accelerate communication with users all around the globe
  - Edge Locations are separate from Regions, so you can push content from a Region into a collection of Edge Locations around the world in order to accelerate communication and content delivery
- **Amazon Route 53**
  - A **Domain Name Service (DNS)** that directs customers to the direct web locations with reliable, low latency
- **AWS Outposts**
  - When a company wants to install and use an AWS on it's premises, AWS will come install the services right inside your own data center
  - Still owned and operated by AWS, but with functionality strict to your premises
  - Not a solution most customers would need

### Key Points

- Regions are geographically isolated areas
- Regions contain Availability Zones, allowing you to run across physically separated buildings 10s of miles apart with single digit latency
- Edge Locations run Amazon CloudFront to help get content to your customers quicker and more reliably anywhere in the world