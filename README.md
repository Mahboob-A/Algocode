                         
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
The Judge is completely isolated and it is only accessible using `events`.  <br/>
Another RCE Engine service for `Java code execution` is under development. 
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

<a href="https://github.com/Mahboob-A/code-manager">Code Manager Service </a> is deployed on `AWS EC2` in Ubuntu 22.04 server.  <br/>

<a href="https://github.com/Mahboob-A/algocode-auth">Algocode Auth Service </a> and <a href="https://github.com/Mahboob-A/rcee/">RCE Engine Service</a> are deployed on `Azure VM` in Ubuntu 22.04 server.  
<br/>
The DNS for the platform `www.algocode.site` is hosted on `Cloudflare`.   

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

####  Prerequisites 

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
  <summary><h3 align="center">API Guideline - Code Submission in Algocode</h3></summary>

> #### Prerequisites 
>
> - I hope you have noted the readily available user account or you have created an account in Algocode. 
> 
>> If you have not done this, please check `API Guideline - Registration in Algocode` section for guideline. 
> 
> - Get the `acces token` using the `user credentials` as per  `API Guideline - Registration in Algocode` section. 
>
> - To submit a solution, you should visit the `notion page` <a href="https://github.com/Mahboob-A/rcee/">Update Me with a notion page link</a> for the available problems in the Algocode. 
> 
>> Go through the problems, and copy the `problem_id` of the problem you want to submit a solution. 
> 
>> Why notion? Did you ask? 
> 
>>> Please check the `Problem Lists` section for information. 

<br/>

### Code Submission in Algocode 

Please follow the below steps to submit a solution in Algocode. 

##### Step 01

Write your solution for the problem you have chosen in `C++`, as currently `C++` is supported. Now, you have to convert it into `JSON` format. As the Algocode does not have client till now, to share data to the backend services, you need to convert it into `JSON`. You can simply make use of `ChatGPT` or `Gemini` for this task. You can share the code to `ChatGPT` or `Gemini` and ask it to convert it into `JSON`. That's it! 

##### Step 02 

As you have copied the `access token` from the `API Guideline - Registration in Algocode` section, please paste the `access token` in `Bearer Token` option in `Auth` section in Postman or Insomnia. 

<br/>

Now, you are ready to submit the solution to the Algocode platform. Please send a `POST` request to the below API following the API reference.

<br/> 

```http
    POST https://codemanager.algocode.site/api/v1/code/submit/
```

| Parameter | Type     | Value/Description                |
| :-------- | :------- | :------------------------- |
| `problem_id`    | `string` | **Required**. The `problem_id` of the problem you are submitting the solution. |
| `lang` | `string` | **Required**. `cpp`. Currently `cpp' is supported. `java` RCE Engine is under development. |
| `code`    | `string` | **Required**. Your solution for the problem in `JSON` format.|

<br/> 

##### Example Payload 

Here's an example payload for one of a problem in Algocode `Sqrt(X)`. The problem is same as this <a href="https://leetcode.com/problems/sqrtx/">Leetcode Problem.</a>

<br/> 

`Example Payload`

```
{
    "problem_id": "f17f511a-8c53-41d3-b750-7673d25835af", 
    "lang": "cpp", 
    "code": "#include <iostream>\n\nint mySqrt(int x) {\n    if (x == 0) return 0;\n    int left = 1, right = x, result = 0;\n    while (left <= right) {\n        
     int mid = left + (right - left) / 2;\n        if (mid <= x / mid) {\n            result = mid;\n            left = mid + 1;\n        } else {\n            right = mid - 1;\n        }\n    
    }\n    return result;\n}\n\nint main() {\n    int t;\n    std::cin >> t;\n    while (t--) {\n        int x;\n        std::cin >> x;\n        std::cout << mySqrt(x) << 
    std::endl;\n    }\n    return 0;\n}\n"
}
``` 
<br/>

##### Response 

Once you have submitted your solution to the Algocode, you will receive a response with a `submission_id`. 
You would be able to see the result of your solution using the `submission_id`.  

<br/>

| Response Key | Type     | Value/Description       |  
| :-------- | :------- | :------------------------- |
| `detail`    | `string` | `Your response has been submitted`|
| `submission_id` | `string` | The `submission_id` of your code solution. |

<br/>

##### Example Response 

```
{
    "result": {
        "detail": "Your response has been submitted.",
        "submission_id": "5993d00f-62fa-437c-8724-ee588265175b"
    }
}
```
<br/>

Please check the `API Guideline - Result Check in Algocode` section to learn how to check the `code submission result.` 
<br/>
<br/>

</details>

