---
layout: post
title: MontGem
feature-img: "img/bloc_api.png"
thumbnail-path: "img/montgem-setup.png"
short-description: JSON Parsing an API

---
## Summary
MontGem is a Ruby Gem API Client with a main function of receiving JSON feedback from Bloc's API. The Gem will be able to interact with the Bloc API by sending & receiving information.

## Problem
The ultimate goal is to build a Gem from scratch which can request and post information through the Bloc API. Below are some of the code challenges that need to be dealt with:
<ol>
    <li>Enabling the gem to interact with the API so it can perform various actions</li>
    <li>Initializing a request and storing the authorization tokens</li>
    <li>Specifying which endpoint the request should target</li>
    <li>Determining what attributes need to be passed in through the body</li>
</ol>

## Solution
The following image depicts the initial setup for the gem. Some modifications were made to the below code.

{:.center}
![]({{ site.baseurl }}/img/montgem-setup.png)

This code is saved into a file: <strong>mont_gem.gemspec</strong> Since other the file is called from a Ruby method, any Ruby actions can be called on this file. It is important to note the .add_runtime_dependency of <a href="https://github.com/jnunemaker/httparty" target="_blank">httparty</a>. This program allows a Ruby interface which deals with the HTTP requests.
~~~
s.add_runtime_dependency 'httparty', '~> 0.13
~~~

To specify where the request will be sent to, I used the following code to simplify the repetitive requests:
~~~
def bloc_api_url(end_point)
  "https://www.bloc.io/api/v1/#{end_point}"
end
~~~
{:.center}
![]({{ site.baseurl }}/img/montgem_json_req.png)

Once this is set up, you can enter the irb console to run the application:
~~~
2.3.0 :001 > require './lib/mont_gem.rb'
 => true 
2.3.0 :002 > MontGem.new("email", "password")
 => #<MontGem:0x00000001190ec8 @auth_token="authorization_token_returned_here">
~~~
If the user exists, the Bloc API returns the authorization token. This is the token that needs to be saved and passed in as a header for later requests.
~~~
@auth_token = response["auth_token"]
~~~
<br>
For every other method to follow, including <strong>get_me</strong>, and <strong>create_message(sender_email, recipient_id, subject, message)</strong>, this <strong>@auth_token</strong> is passed through to gain initial access to the API request. The user must include the appropriate parameters, whether they are a string or a number, in order to complete the request.

## Results
The end result is a fully operational Gem program which has the ability to interact with the <a href="http://docs.blocapi.apiary.io/#reference/0/sessions/retreive-auth-token" target="_blank">Bloc APIARY</a>. Once the @auth_token is saved, the Gem can commit GET or POST http actions upon user request.
## Project Conclusions
This project helped me develop a greater understanding of how to construct and control a gem API program. I'm certain the experience of working this closely with JSON and an API client will help me in the future.



