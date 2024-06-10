                         
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
Another service for Java code execution is under development. 

The <a href="https://github.com/Mahboob-A/rcee/">RCE Engine </a> of Algocode can execute user codes and run test cases against the code output. 

The Online Judge of <a href="https://github.com/Mahboob-A/rcee/">RCE Engine </a> service can handle the below events: 

    a. AC (Accepted) 
    b. WA (Wrong Answer)
    c. Compilation Error 
    d. Time Limit Exceed 
    e. Memory Limit Exceed 
    f. Segmentation Fault

**The Online Judge used in *<a href="https://github.com/Mahboob-A/rcee/">RCE Engine </a>* is a pure docker implementation and no other 3rd party API or service has been used.**

> Please refer to the respective services to learn more about them. You will find rich and detailed documentation in the respective service's github repository, I promise!  <br/>
<br/>
<h3 align="center">Deployment</h3>

#### Deployment Information 

All the services in this project is deployed in  `AWS EC2`  or `Azure VM` in Ubuntu server 22.04.  <br/>
The DNS is hosted in `Cloudflare`.   

<br/>
<br/>
<h3 align="center">Problem Lists</h3>

#### Small Note

> As of today I have build the backend in microservices, there's no frontend for the project. I am fully focusing on the advanced backend engineering, hence, if you want to contribute or want to build a frontend for the project, please do not hesitate to email me here: 
> [![Email Me](https://img.shields.io/badge/mahboob-black?style=flat&logo=gmail)](mailto:connect.mahboobalam@gmail.com?subject=Hello)
<br/>

#### Problem Lists in Algocode 

I have prepared a Notion Page for all the problems currently available in the Algocode project. Please visit this link <a href="https://github.com/Mahboob-A/rcee/">Update Me with a notion page link</a> to get the information. <br/> <br/> 
You will need to visit this page in order to submit your solution. Just read the problem statements, understand the problem, and copy the `problem id`. That's all you need to submit a solution! <br/><br/>
 Please read below for detailed guide on how to submit a solution in the *Algocode* platform. 

<br/>
<br/>
<h3 align="center">API Guideline - How to Submit Solution </h3>

###  Prerequisites 

You will need `postman` or `insomnia` to submit a solution to the project. I know you do have postman or insomnia! 

Please open postman or insomnia, and continue reading ...  

<br/>

###  Step 01 - Register in the Algocode Platform

<a href="https://github.com/Mahboob-A/algocode-auth">Algocode Auth Service </a>  is handling the user management. 

You have two ways to submit a solution to the `Algocode` platform. You can create your own account, or you can use the `already available verified  account`.  

<br/>

#### A. By Using Ready to Use Account Details 

Please copy the account details and the login endpoint. 

Send a `POST` request to the endpoint, and you'll receive `access token` and `refresh token`. 

Copy the `access token` and head on to the `Step 02` below.

`Login Endpoint`: `https://auth.algocode.site/api/v1/auth/login/`

`Account Credentials`: 
```
"email": "mehboob@gmail.com", 
"password": "12345678@1"
```
<br/>
 
#### B. By Registering in the Algocode Platform

If you want to use your own account so submit solutions, please create an account. 

Creating account involves two steps: 

- submit the from 

- verify your email address 

<br/>

###### a. Submit The Form 

Copy the below submit endpoint along with the `JSON` data format, and send a `POST` request. 

> Please provide your real email address you'll receive `a token` in your email from the Algocode Auth domain `auth.algocode.site`. 

`Registration Endpoint`: `https://auth.algocode.site/api/v1/auth/registration/`

`Payload`

```
"username": "YOUR_USER_NAME", 
"email": "YOUR_AUTHENTIC_EMAIL_ADDRESS",
"password1": "YOUR_PASSWORD",   // complex password with special characters like @ 
"password2": "CONFIRM_PASSWORD",
"first_name": "YOUR_FIRST_NAME",
"last_name": "YOUR_LAST_NAME"
```
<br/>

###### b. Check Email for Token 

At this time please check your email address, you will have received an email from `auth.algocode.site` domain. 

The email will have the below URL to validate your account activation. As Algocode does not have any frontend, we need to verify the account manually. 

`Example Token URL`: 

```
To confirm this is correct, go to https://auth.algocode.site/api/v1/auth/registration/account-confirm-email/Mw:1sFEOr:xsqvnifUV5ppDFqbQBrmp2sIXGoRY63BmnFddsYTau4/
```

Open the email, and copy everything after the endpoint i.e. `https://auth.algocode.site/api/v1/auth/registration/account-confirm-email/` 
For the above example, copy `Mw:1sFEOr:xsqvnifUV5ppDFqbQBrmp2sIXGoRY63BmnFddsYTau4`. 

Send a `POST` request to the below endpoint to validate your account creation. 

`Account Validation Endpoint`: `https://auth.algocode.site/api/v1/auth/registration/verify-email/`

`Payload`

```
{
	"key": "YOUR_COPIED_KEY_FROM_EMAIL"
}
```

`Response`

```
{
	"detail": "ok"
}
```
If you have received the response as `ok`, congratulation on creating your account on Algocode!

You can now login to your account with the `login endpoint` mentioned above to get `access token`.

But in case you were not able to create account, please `raise an issue` and use the `ready to use account` instead. 

