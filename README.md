# airesearch : Assisting reseachers with LLM’s 

# Demo
<video 
src="documentations/Palooza Handson Demo.mp4">
</video>


# Introduction

Our innovative AI-driven research assistant is tailored to provide researchers with powerful and efficient resources for effectively exploring the constantly evolving realm of scientific literature. Researchers often face the daunting task of staying up-to-date with emerging breakthroughs across diverse fields. This challenge can be overwhelming as they sift through numerous papers, each filled with distinct terminology and formatting conventions.
Conducting a comprehensive literature review and analysis becomes particularly challenging when dealing with a large volume of papers. Identifying seminal papers within a specific domain is equally arduous. Drawing meaningful conclusions from this extensive ocean of papers and identifying research gaps is a time-consuming process that demands creativity and expertise.
As the NASApalooza team, we address these challenges with a multifaceted approach. At its core, we've developed Palooza, an interactive web application that serves as the researcher's command center. This intuitive platform provides researchers with quick access to comprehensive insights and summaries of research papers relevant to their chosen domains. By utilizing Palooza, researchers can efficiently identify whitespace in research, draw conclusions from a vast ocean of papers, and explore research topics in less time.
Our platform also enables researchers to effortlessly navigate mind maps connecting related research topics and delve into nested citations, providing a deeper understanding of the interconnectedness of ideas. Additionally, we offer Q&A sessions on papers and quick analysis of datasets, further enhancing the research experience.

# Problem Statement

Researchers face significant challenges in maintaining up-to-date knowledge of emerging scientific and technological advancements and applying them to their missions. These challenges stem from the need to comprehend extensive research literature, both within and outside their areas of expertise. The current workflow involves running multiple queries on public and commercial databases, resulting in the retrieval of hundreds of papers. Researchers must then assess the relevance of these papers based on their titles, abstracts, and metadata. 
To synthesize relevant information, researchers are required to read or at least walkthrough hundreds of papers, navigating diverse reporting standards and disciplinary jargon. Consequently, a substantial amount of time and effort is invested in reviewing information that often proves irrelevant or non-useful. This inefficiency hinders their ability to harness the vast and continually expanding body of scientific literature.

In summary, the key pain points for researchers include:
1.	Information Overload
2.	Time-Consuming Review
3.	Interdisciplinary Challenges
4.	Relevance Filtering
5.	Efficiency Gap

# Proposed Approach

To address the challenges faced by researchers in managing and extracting insights from the vast scientific literature, we propose the development of Palooza, an interactive web application with a comprehensive set of features designed to streamline the research process and enhance efficiency. Palooza's features are specifically tailored to cater to the pain points outlined in the problem statement.
1.	Paper Retrieval
2.	Paper Analysis
3.	Questioning & Answering (Q&A)
4.	Document Analysis
5.	Dataset Analysis
6.	Author Analysis
7.	Mindmap
8.	Keyword Extraction and Annotation
9.	Literature Review
10.	Topic Trend Analysis
11.	Relevant Searches
12.	Bookmark and Favorite List
    

The following diagram represents the behavior of the Palooza application:




![Architecture](https://github.com/connectaman/Palooza/blob/d9e5adc3a37111074c6c9576a6650572d68d8537/documentations/UML.png)


#### Deployment Features and Consideration for Palooza Application: 

Cloud Agnostic and easy deployment

![Architecture](https://github.com/connectaman/Palooza/blob/5d9acbf0bfb518b7a2cc23792ad075110a250d5a/documentations/deployment%20arch.png)

#### Can cater up to hundreds of thousands of users? 
The deployment approach utilized plays a pivotal role in ensuring our application's readiness to cater to millions of users. By embracing a cloud-agnostic architecture founded on microservices and containerization, we've laid the groundwork for remarkable scalability. This strategy allows us to efficiently scale individual components of the application to meet increased demand, ensuring optimal performance and responsiveness as our user base expands.

#### Comparing Palooza to Other Available Applications

![Comparing](https://github.com/connectaman/Palooza/blob/d9e5adc3a37111074c6c9576a6650572d68d8537/documentations/comparision.png)

# Future Enhancement:

In addition to the existing features, we plan to implement several advanced enhancements in current Palooza application:

-	Complex and Domain-Specific Retrieval
-	Advanced Mind Maps
-	Universal Retrieval Engine Support
-	UI Enhancement
-	Diverse Data Source Integration
-	Advanced Table Comparison View
-	Downloading Reports
-	Database Integration for User Login
These enhancements will make Palooza an even more powerful tool for researchers, providing a seamless and comprehensive research experience across diverse domains.



# Steps to Deploy:

- Dependencies
    - python>=3.10
    - nodejs
    - docker

## Backend FastAPI

- Step 1: Redirect to palooza-backend directory
```
cd palooza-backend/
```
- Step 2: Export env variables
```
export OPENAI_API_KEY=""
export SERP_API_KEY=""
export GOOGLE_CSE_ID=""
export GOOGLE_API_KEY=""
```
- Step 3: build the docker image
```
docker build -t palooza:latest .
```
- Step 3: run the docker image
```
docker run -d -p 8000:8000 palooza:latest .
```


## FrontEnd UI

- Step 1: Redirect to palooza-frontend directory
```
cd palooza-frontend/
```
- Step 2: Install all the required packages
```
npm install
```
- Step 3: Change the Backend API url from the above steps
```
nana src/Config/config.js
```
- Step 3: Start the server
```
npm start
```

# Key points to note:
- You might be wondering why we use the SERP API. Well, we initially attempted web scraping using the **Beautiful Soup 4** library to download papers from Google Scholar. However, we encountered issues with Cloudfare and Captcha. Consequently, we transitioned to using the SERP API to download papers from Google Scholar.
- We retrieve the most recent papers (recently published) and perform analysis using GPT models. While using GPT models alone, we are unable to access the latest information as they are trained on data only up to September 2021.


# Screenshots

|Screenshots|Screenshots|
|----|----|
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(1).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(2).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(3).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(4).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(5).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(6).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(7).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(8).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(9).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(10).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(11).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(12).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(13).png)  |  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(14).png)  |
|  ![1](https://github.com/connectaman/Palooza/blob/d50c81814744a0e5f40200113476b0280bfade1e/screenshots/palooza%20screenshot%20(15).png)  |  .. |



