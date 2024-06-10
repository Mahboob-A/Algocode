                         
<br/>
<div align="center">
<a href="https://github.com/Mahboob-A/algocode">
<img src="https://github.com/Mahboob-A/algocode/assets/109282492/cd5d981f-1928-49a1-a4d8-0a5b21b92171" alt="Logo" width="700" height="400">
</a>
<h3 align="center">Algocode - The Leetcode for Hackers</h3>
<p align="center">
Algocode is a DSA practice platform just like Leetcode!
<br/>
<br/>
<a href="https://github.com/Mahboob-A/algocode-auth"><strong>Read the blog »</strong></a>
<br/>
<br/>
<a href="https://github.com/Mahboob-A/algocode-auth">Algocode Auth Service .</a>  
<a href="https://github.com/Mahboob-A/code-manager">Code Manager Service .</a>
<a href="https://github.com/Mahboob-A/rcee/">RCE Engine Service</a>
</p>
</div>
<br/>
<br/>
<h3 align="center">General Information</h3>

Algocode is an online data structure and algorithm practice backend built in microservices architecture. 


*Algocode currently has three services*: <a href="https://github.com/Mahboob-A/algocode-auth">Algocode Auth Service .</a> <a href="https://github.com/Mahboob-A/code-manager">Code Manager Service .</a> and <a href="https://github.com/Mahboob-A/rcee/">RCE Engine Service</a>
<br/> <br/>

* <a href="https://github.com/Mahboob-A/algocode-auth">Algocode Auth Service </a> Auth Service handles user management.

* <a href="https://github.com/Mahboob-A/code-manager">Code Manager Service </a> Code Manager Service handles `code submission`, 
`code exec event creation to Message Queue`, and `saving and caching code executing result` to Database.

* <a href="https://github.com/Mahboob-A/rcee/">RCE Engine Service</a> RCE Engine Service contains the `C++` code execution Judge. 
The Judge is completely isolated and it is only accessible using `events`. Another RCE Engine service for `Java code execution` is under development. 
<br/> <br/>

The `C++ Judge` of <a href="https://github.com/Mahboob-A/rcee/">RCE Engine </a> can execute `C++`  codes and run test cases against the code output. It can currently  handle the below events: 

    a. AC (Accepted) 
    b. WA (Wrong Answer)
    c. Compilation Error 
    d. Time Limit Exceed 
    e. Memory Limit Exceed 
    f. Segmentation Fault

#### *NOTE* 

**The `C++ Judge` in *<a href="https://github.com/Mahboob-A/rcee/">RCE Engine </a>* is a pure docker implementation and no other 3rd party API or service has been used.**

> Please refer to the respective services to learn more about it. You will find rich and detailed documentation in the respective service's github repository, I promise!  <br/>
<br/>
<details>
<summary><h3 align="center">Deployment</h3></summary>

#### Deployment Information 

All the services in this project are deployed in  `AWS EC2`  or `Azure VM` in Ubuntu server 22.04.  <br/>
The DNS is hosted in `Cloudflare`.   

</details>
<br/>
<br/>
<details>
<summary><h3 align="center">Problem Lists</h3></summary> 

#### Small Note

> As of today I have built the backend in microservices, there's no frontend for the project. I am fully focusing on the advanced backend engineering, hence, if you want to contribute or want to build a frontend for the project, please do not hesitate to email me here: 
> [![Email Me](https://img.shields.io/badge/mahboob-black?style=flat&logo=gmail)](mailto:connect.mahboobalam@gmail.com?subject=Hello)
<br/>


#### Problem Lists in Algocode 

I have prepared a Notion Page for all the problems currently available in the Algocode project. Please visit this link <a href="https://github.com/Mahboob-A/rcee/">Update Me with a notion page link</a> to get the information. <br/> <br/> 
You will need to visit this page in order to submit your solution. Just read the problem statements, understand the problem, and copy the `problem id`. That's all you need to submit a solution! <br/><br/>
 Please read `API Guideline - Registration in Algocode` for account details  and 
`API Guideline - Code Submission in Algocode` for detailed guide on how to submit a solution in the *Algocode* platform. 

</details>
<br/>
<br/>

<details>
  <summary><h3 align="center">API Guideline - Registration in Algocode</h3></summary>

###  Prerequisites 

You will need `postman` or `insomnia` to submit a solution to the project. I know you do have postman or insomnia! 

Please open postman or insomnia, and continue reading ...  

<br/>

###  Registration in the Algocode Platform

> The <a href="https://github.com/Mahboob-A/algocode-auth">Algocode Auth Service </a> is handling the user management. 
> 
> To Know more on the `Algocode Auth Service` please visit the repository. 

You have two ways to submit a solution to the `Algocode` platform. You can create your own account, or you can use the `already available verified  account`.  

<br/>

#### A. By Using Ready to Use Account Details 

Please copy the account details and the login endpoint. 

```http
  POST https://auth.algocode.site/api/v1/auth/login/
```

| Parameter | Type     | Value                |
| :-------- | :------- | :------------------------- |
| `email`    | `string` |  `connect.mahboobalam@gmail.com`  |
| `password` | `string` | `12345678@1`|


Send a `POST` request to the endpoint, and you'll receive `access token` and `refresh token`. 

Copy the `access token` and head on to the `API Guideline - Code Submission in Algocode` section below.

<br/>
 
#### B. By Registering in the Algocode Platform

If you want to use your own account to submit solutions, please create an account. 

Creating account involves two steps: 

- submit the from 

- verify your email address 

<br/>

###### a. Submit The Form 

Copy the below submit endpoint along with the `JSON` data format, and send a `POST` request. 

> Please provide your **authentic email address** as you'll receive `a token` in your email from the Algocode Auth domain `auth.algocode.site`. 

<br/>

```http
    POST https://auth.algocode.site/api/v1/auth/registration/
```


| Parameter | Type     |        Description                |
| :-------- | :------- | :------------------------- |
| `username`    | `string` | **Required** Your username for the account.  |
| `email`    | `string` | **Required** Your valid email address.|
| `password1`   | `string` | **Required** Your password. | 
| `password2` | `string` |  **Required** Confirm your password. | 
| `first_name` | `string` | **Required**  Your first name. | 
| `last_name` | `string` | **Required** Your last name. | 


<br/>

###### b. Check Email for Token 

At this time please check your email, you will have received an email from `auth.algocode.site` domain. 

The email will have  an email validation URL to validate your account activation. *Do not click the URL*

As Algocode does not have any frontend, you need to verify the account manually. 

`Example Token URL`: 

```
To confirm this is correct, go to https://auth.algocode.site/api/v1/auth/registration/account-confirm-email/Mw:1sFEOr:xsqvnifUV5ppDFqbQBrmp2sIXGoRY63BmnFddsYTau4/
```

Copy everything after the account validation URL endpoint i.e. `https://auth.algocode.site/api/v1/auth/registration/account-confirm-email/` 

For the above example, copy `Mw:1sFEOr:xsqvnifUV5ppDFqbQBrmp2sIXGoRY63BmnFddsYTau4`. 

<br/>

Send a `POST` request to the below endpoint to validate your account creation. 

```http
    POST  https://auth.algocode.site/api/v1/auth/registration/verify-email/

```

| Parameter | Type     |  Value                |
| :-------- | :------- | :------------------------- |
| `key`    | `string` | **Required**. Your copied token from your email  |

***Response***

| Response Key | Type     |        Value            |        Description        | 
| :-------- | :------- | :------------------------- |:------------------------- | 
| `detail`    | `string` |  `OK`                     | Registration is successful!|
| `detail`    | `string` |   Any value other than `OK` | Registration is unsuccessful. Check the token again.|

<br/>

If you have received the response as `ok`, congratulation on creating your account on Algocode! 

You can now login to your account with the `login endpoint` mentioned above to get `access token` and 

head on to the `API Guideline - Code Submission in Algocode` section below.

<br/>

> But in case you were not able to create account, please `raise an issue` and use the `ready to use account` instead. 

<br/>

</details>
<br/>
<br/>

<details>
  <summary><h3 align="center">API Guideline - Registration in Algocode</h3></summary>
