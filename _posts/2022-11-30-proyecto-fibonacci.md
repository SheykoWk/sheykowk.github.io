---
layout: post
title:  "Fibonacci API"
date:   2022-11-30
excerpt: "Creating of Fibonacci API"
tag:
- English 
- Backend
- Documentacion
- Node
- Express
project: true
comments: false
---
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/SheykoWk/Fibonacci-API">
    <img src="https://i.imgur.com/TK4rqUU.png" alt="Logo" width="80px" height="80px">
  </a>

  <h3 align="center">Fibonacci API</h3>

  <p align="center">
    Rest API that accepts a number, n, as input and returns the number in the n position on Fibonacci sequence.
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project Solution</a>
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
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

I'd started creating all the testing for my API, making unit and integration testing for the generate Fibonacci function and for the requests
My first option was to make a recursive function but it takes so much time and has more algorithm complexity, so I decided to make it save all the values in an array to make it more fast and optimized
I start with error management, so the different input cases are the next ones:
    - Receive NaN values
    - Receive Negative values
So if I make the second error management I can validate both errors




### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* <img src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E" /> 
* <img src="https://img.shields.io/badge/Express%20js-000000?style=for-the-badge&logo=express&logoColor=white"/>   
* <img src="https://img.shields.io/badge/Mocha-8D6748?style=for-the-badge&logo=Mocha&logoColor=white" />   
* <img src="https://img.shields.io/badge/chai-A30701?style=for-the-badge&logo=chai&logoColor=white" />  




<!-- GETTING STARTED -->
## Getting Started

How you can use this project locally?

### Prerequisites

This a is project made with JavaScript, so the first thing that you need is the latest npm version.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation


1. Clone the repo
   ```sh
   git clone https://github.com/SheykoWk/Fibonacci-API.git
   cd Fibonacci-API
   ```
2. Install NPM packages
   ```sh
   npm install
   ```
3. Generate your `.env` file
   ```sh
   cp .env.example .env
   ```




<!-- USAGE EXAMPLES -->
## Usage

* To deploy your app in a dev environment
   ```sh
   npm run dev
   ```
* To deploy your app in a production environment
   ```sh
   npm start
   ```
* To run the tests
   ```sh
   npm run test
   ```

1. You can make requests to the next url
    - GET /api/v1/fibonacci/<Number> type: application/json
        response: 
```json
{
    "error": false,
    "status": 200,
    "data": <Fibonacci Value>
}
```







