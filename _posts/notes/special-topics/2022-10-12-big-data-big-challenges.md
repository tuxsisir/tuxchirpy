---
title: "Big Data, Big Challenges and an Introduction to Data Lake"
date: 2022-10-12
tags: ["data-analytics", "special-topics", "study-notes"]
categories: [analytics]
image: https://source.unsplash.com/gpjvRZyavZc/800x300
pin: true
---

## Big Data

Big Data refers to the amount of data with greater variety, higher volume and data being generated at high-level frequency.
We are currently in the digital age where we are having data input from variety of sources, cell phones, IoT (smart devices) attached at every
intersection of our lives, point-of-sales (POS) systems, health trackers, smart watches, social media usage, data collection from vehicles, banking systems,
customer logs, emails, server logs and so much more. We have digital data being generated from two major sources either offline or online. Technically, big data
is born online. Big Data is the intensity of this data which is greater in terms of _volume, velocity, variety, and veracity_. Big Data is not a single technology rather
a practice that is applied across many areas of Business and Technology.

## **Challenges of Big Data in terms of Data Generation, Retrieval and Storage**

The lack of understanding in dealing with big data opens a list of data challenges. As companies start moving to digital products that use big data, their
employees or workforce may not be ready to use such advanced solutions which can lead to significant workflow delays, interruptions to familiar workflows,
and numerous errors. Until employees get the most out of innovation and learn how to use it, productivity can suffer. In addition to developing and deploying new
advanced digital solutions for Big Data challenges, attracting qualified professionals, or training existing ones in current workflows is critical to overcoming
these data challenges.

### Data Generation

One of the challenging phases in Big Data is how the companies are generating data in terms of future purposes regarding making use of their data on the long run.
Typical problems for big data processing companies are data warehouses with poor data quality: it may have unstructured data, data with different formats, contain
duplicate records, data integrity errors etc. As a result, the data cannot be accessed centrally or synchronized with each other. Before consuming huge amounts of
unstructured data from different formats and sources, they must be examined, formatted, and if necessary, cleaned. Deleting data takes a long time, and only then can
it be used in software algorithms. For example, processing data with a particular algorithm can take only a few minutes, while preliminary cleaning can take weeks.

### Data Retrieval

Real-time data can be a very complex and sophisticated issue in terms of big data retrieval. Whenever we refer data retrieval, it is not always the case of stagnant data and processing over it. Big Data deals with data that is constantly being updated every second and companies need to be aware of this too. It is important for companies to keep up to date with real time data, as well as "stagnant" data, and readily available systems to process these data. This will result in better information gathering and improved decision-making.

### Data Storage

Companies planning to store large amounts of data, will need the infrastructure to store it, which often means investing in high-tech servers that will take up significant space in an office or building. If the data is stored somewhere remote, then there may be a security concerns on third party access. If there are many layers of security that can help prevent this unauthorized access, including encryption and reliance on third-party vendors, but there's a limit to how much it can protect. To overcome security challenges remotely, companies need to manage operations closely, choose the best partners, and ensure that their team always adheres to best practices.

## Data Lake

A data lake is a centralized data repository where datasets from multiple sources are stored in their original structure at any given scale. Data from multiple sources can be both structured and unstructured data. Data Lake systems provide functions to extract data and metadata from heterogeneous sources and run different types of analytics – from big data processing to visualizations, dashboards, and machine learning to guide for better decisions. Unlike data warehouses, data lakes excel at using large amounts of available consistent data along with deep learning algorithms to help with real-time decision analysis.

### Data Accessible for Everyone with Data Lake

Often only the top executives in an organization have the leverage of getting the access of the crucial data to make valuable decisions for their organization. In the process, middle management decision making is overlooked, and they are not able to get their hands on their required data in limited time. Data Lake makes the accessibility of data to every level user (Business Analyst, Data Engineers, Data Scientists, and others) of the organization to make their impact based on data. With the necessary data available to all the users from wide hierarchy of the organization, everyone can make a viable decision at their level.

## **Building Technology Stack for Data Lakes**

Data Lake is a complex technology and requires integration of multiple technologies for ingest, processing, and discovery. In addition, there are no standard rules for security, governance, operations, and collaboration. Ultimately, the data lake solution must be scalable from a single user to thousands of users and from a kilobyte of data to several petabytes of data. As the Big Data industry is changing rapidly, choosing technology that is persistent and powerful is crucial. There are two primary infrastructures for building technology stack for data lakes:

1. On Premises Data Lakes
2. Cloud Data Lakes

### **On Premises Data Lakes**

On premise data lake systems are geared for the large corporations where initial investment is substantially high and maintaining the on-premises data lake is significantly hard. On-premises data lakes require tight control of resource usage and are expensive. Data lakes are traditionally deployed on-premises, with storage on HDFS and processing (YARN) on Hadoop clusters. Hadoop is scalable, inexpensive, and collection of software utilities that offers good performance with its inherent data localization advantage (data and computer reside together). Major issue when it comes to on-premises data lake is the scalability because it's important to properly estimate hardware requirements early in the project. As data grows unsystematically every day, this is a difficult issue to achieve success over with manually adding and configuring servers which requires huge amount of manpower and investment that comes along with it.

### **Cloud Data Lakes**

Most of the organizations are migrating to cloud data lakes because of their hassle-free infrastructure building and maintenance which results in freeing up organization's engineering resources to foster a culture of innovation across the value chain. With cloud data lakes companies can reduce engineering costs by using data lakes to develop data pipelines easily and efficiently. This saves a significant amount of time and effort, allowing organizations to scale quickly. Some of the top cloud data lake vendors are _Amazon Web Services (AWS) Data Lake, Cloudera, Google Cloud, IBM, Microsoft Azure, Oracle._

With all the vendors available in the cloud for data lakes, there are many factors a company should weigh in while choosing the right technology stack for cloud data lake to implement. It can be from the range of services that the cloud service is providing from cost efficiency and likelihood of available options that the company might need in the future.

## **Challenges of Cloud Data Lakes**

Without the right tools, data lakes can experience reliability issues, making it difficult for data scientists and analysts to reason about the data. The main challenge of a data lake architecture is that raw data is stored without content monitoring. For a data lake to make data usable, it must have defined mechanisms for cataloging and securing the data. Without these, the data is unretrievable or unreliable, resulting in a "data swamp". To meet the needs of a wider audience, data lakes must have governance, semantic consistency, and access control capabilities.

Data lakes can hold huge amounts of data, and businesses need ways to reliably perform update, merge, and delete operations on that data so they stay up to date. With traditional data lakes, it can be extremely difficult to perform simple operations like these and confirm that they succeeded, as there is no mechanism in place to ensure data consistency. Without such a mechanism, it would be difficult for data scientists to make inferences about their data.

## **Amazon Web Services (AWS) Data Lake - Industry Leading Cloud Data Lake**

AWS provides an automated, cost-effective, and highly available data lake architecture with an easy-to-use console to search and
query real-time data sets. With AWS Data Lake setup for an organization, users can catalog, upload, new datasets of any size with
searchable metadata as well as for the existing data of organization's S3 pool without additional effort. Amazon ecosystem wraps every
other amazon services within the data lake efficiently and makes an integration well for users to work, collaborate and analyze data. Under Amazon Cloud
Computing Services, we can make use of and integrate plethora of services provided by Amazon to make the optimal use of data lake for the organization.

![AWS: What is a data lake?](https://d1.awsstatic.com/AWS_Analytics_2021_LakeHouse.337c5d294eae24fe954c1d2e93fcda03233dfba4.png)
_Source: https://aws.amazon.com/big-data/datalakes-and-analytics/what-is-a-data-lake/_
<center><i>Fig. AWS Data Lake Overview</i></center>


From migration of on-premises data to cloud, implementing machine learning models over historical data of the organization with visualizations to dashboards and getting valuable analytics over the organizational data are some of the key factors which is driving today's data lake trend to move over to cloud from on-premises stack. One of the cost-efficient factors that cloud based data lake provides is that the billing costs of services are based on the actual utilization of the services. This makes the overall process of migrating to cloud-based data lake makes more desirable.

## **Building data lake on AWS**

Base services that we need to use on Amazon Web Services to create a data lake stack are **Amazon S3 (Simple Storage Service)**
to store unlimited data storage, **Amazon Cognito** for authentication, **Amazon Elasticsearch** for better searching capabilities, **AWS Lambda**
for running individual microservices, **AWS Glue** for data transmission and **Amazon Athena** for data analytics. We can also add or remove services
based on the need of the organization. These services are some of the basics to implement data lake on AWS.

![Data Lake on AWS Architecture](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/data-lake-architecturev2.dbc0d40c45245a3fbfc111341c72e9a52e8df308.png){: width="70%"}
_Source: [https://aws.amazon.com/solutions/implementations/data-lake-solution/](https://aws.amazon.com/solutions/implementations/data-lake-solution/)_
<center><i>Fig. Data Lake on AWS Architecture</i></center>

## **Data Lake Trends with Amazon Web Services (AWS)**

AWS is a widely adopted choice for cloud data lake system because it provides three of the most core features required for any organization to scale along with their organizational growth, i.e., Flexibility, Comprehensiveness, Security and Governance. AWS supports large volume of data to store regardless of its volume or format. It is also equipped all the services, flexibility to add in or remove services along with the cost efficiency mechanism of pay as per the utilization and supports easy encryption for other security concerns.

Organizations are using Data Lakes, most likely cloud-based Data Lake systems to power their organization and drive data culture in the organization to provide data access to every level of their users to make valuable impact for their growth. Data in an organization should be available to all the users to make viable decisions to have impact on the organization. They allow users to collaborate and analyze data in a variety of ways, helping to make better and faster decisions. The ability to leverage more data, from more sources, in less time and to allow users to collaborate and analyze data in different ways leads to better and faster decision making.

## **References:**

1. Times of India Article (2022). _How data lakes can empower enterprises_. [online] Available at: [https://timesofindia.indiatimes.com/readersblog/blogger-park/how-data-lakes-can-empower-enterprises-44645/](https://timesofindia.indiatimes.com/readersblog/blogger-park/how-data-lakes-can-empower-enterprises-44645/).

2. Amazon Web Services, Inc. (n.d.). _Data Lake - Implementations - AWS Solutions_. [online] Available at: [https://aws.amazon.com/solutions/implementations/data-lake-solution/](https://aws.amazon.com/solutions/implementations/data-lake-solution/).

3. AWS (2019). _What Is a Data lake?_ [online] Amazon Web Services, Inc. Available at: [https://aws.amazon.com/big-data/datalakes-and-analytics/what-is-a-data-lake/](https://aws.amazon.com/big-data/datalakes-and-analytics/what-is-a-data-lake/).

4. Mahmoudzadeh, P. (2019). _Building a Data Lake on AWS_. [online] Medium. Available at: [https://medium.com/@pmahmoudzadeh/building-a-data-lake-on-aws-3f02f66a079e](https://medium.com/@pmahmoudzadeh/building-a-data-lake-on-aws-3f02f66a079e).

5. Databricks. (n.d.). _Introduction to Data Lakes_. [online] Available at: [https://www.databricks.com/discover/data-lakes/introduction#challenges](https://www.databricks.com/discover/data-lakes/introduction#challenges)

6. Sisense. (2018). _4 Trends Driving Growth in Cloud Data Lakes l Sisense_. [online] Available at: [https://www.sisense.com/blog/4-trends-driving-growth-cloud-data-lakes/](https://www.sisense.com/blog/4-trends-driving-growth-cloud-data-lakes/).

7. Krishna, S. (2022). _Are on-premises data lakes becoming obsolete?_ [online] Analytics India Magazine. Available at: [https://analyticsindiamag.com/are-on-premise-data-lakes-becoming-obsolete-%EF%BF%BC/](https://analyticsindiamag.com/are-on-premise-data-lakes-becoming-obsolete-%EF%BF%BC/).

8. Talend Real-Time Open-Source Data Integration Software. (n.d.). _What is a Data Lake? - Talend_. [online] Available at: [https://www.talend.com/resources/what-is-data-lake/](https://www.talend.com/resources/what-is-data-lake/).

9. MongoDB White Paper. (2016). _Big Data: Examples and Guidelines for the Enterprise Decision Maker_. [online] Available at: [https://www.mongodb.com/](https://www.mongodb.com/).

10. IBM White Paper. (2012). _Choosing a big data technology stack for digital marketing_. [online] Available at: [https://www.ibm.com](https://www.ibm.com/).

11. Cunningham, N. (2022). _Top 10 data lake solution vendors in 2022_. [online] VentureBeat. Available at: [https://venturebeat.com/data-infrastructure/top-10-data-lake-solution-vendors-in-2022/](https://venturebeat.com/data-infrastructure/top-10-data-lake-solution-vendors-in-2022/).

12. Alton, L. (2018). _The 7 Biggest Problems in Data Storage - and How to Overcome Them - SmartData Collective_. [online] SmartData Collective. Available at: [https://www.smartdatacollective.com/7-biggest-problems-data-storage-overcome/](https://www.smartdatacollective.com/7-biggest-problems-data-storage-overcome/).
