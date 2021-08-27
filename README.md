# Around-Video-Website

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project


This is a scalable web application using Go and ReactJS to handle video posts and deployed it on Google Cloud, it using token-based with React Router and server-side user authentication with JWT and ElasticSearch to provide search functions so that users can get the corresponding videos, also there is a message queue using RabbitMQ as an intermediary for messaging to achieve non-blocking notifications
<br/>
This is repo is about the backend that use go, to see the detail of the frontend taht use React, click this link : [video_server_frontend](https://github.com/ZLi0111/video_server_frontend)

### Built With

* [Golang](https://golang.org/)
* [RabbitMQ](https://www.rabbitmq.com/)
* [ElasticSearch](https://www.elastic.co/?ultron=B-Stack-Trials-AMER-US-W-Exact&gambit=Stack-Core&blade=adwords-s&hulk=cpc&Device=c&thor=elasticsearch&gclid=CjwKCAjwmqKJBhAWEiwAMvGt6ErnplZkgpGHbNLo2dV1MkyIuQs0tfzMWCiMaIuZg4lgAUcrhiWzFhoCvQ8QAvD_BwE)



<!-- GETTING STARTED -->
## Getting Started


### Prerequisites

This repo is depolyed in the GCP, to make it work properly, please use google store app engine and storage in the following link:

* [GCP App Engine](https://cloud.google.com/appengine/docs)
* [GCP stroage](https://cloud.google.com/storage/docs/)

Question: Why not store media files in database directly?
<br />
First, it’s much slower to store media files in a database than store in a file system directly. Second, media files will increase the size of the database a lot which will make it hard for maintenance. Third, there’s no way to do database related optimization(e.g. indexing) based on a binary file.
<br />
GCS is good for media files because it behaves like a file system, has good availability and durability, is less expensive and also provides CDN service to serve files in edge servers to reduce loading latency.


### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/ZLi0111/Around-Video-Website.git
   ```
2. run the index.go in the index folder first
   ```sh
   go run index.go
   ```
3. then run all the go doc in the project folder
   ```sh
   go run *.go
   ```



<!-- USAGE EXAMPLES -->
## Usage

This backend will return the Restful API that makes good data communication with frontend, here is the list of the API

* user: 
  ```
  URL:/user Method:POST,SC:201,400,500
  URL:/user/:username Method: POST,SC:200,400,500
  URL:/user/:username Method: GET, SC:200, 400, 401, 403, 500
  URL:/user/:username Method: DELETE, SC:204, 400, 401, 403, 500
  ```
* video/image:
  ```sh
  URL:/videos/:vid-id Method: GET, SC:200, 400, 401, 403, 500
  URL:/upload/:vid-id Method: POST, SC:200,400,500
  URL:/delete/:vid-id Method: DELETE, SC:204, 400, 401, 403, 500
  ```



<!-- CONTACT -->
## Contact

Zhengrong Li - email: Zhengrongli1003@gmail.com

Project Link: [https://github.com/zli0111/Around-Video-Website](https://github.com/zli0111/Around-Video-Website)

Personal website: [zli0111](http://zli0111.com)

Linkedin: [in/zli0111/](https://www.linkedin.com/in/zli0111/)