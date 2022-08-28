# OAuth

## What Is OAuth and Why to use?

A technological standard that allows you to share information between services without exposing your password. 


The simplest example of OAuth is when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you, and the website you were originally connecting to logs you on itself afterward using permission gained from the second website.


## OAuth and APIs, How OAuth Is Used to Access APIs?

OAuth is about authorization, not authentication.
Authorization:  is asking for permission to do stuff.
Authentication: Proving you are the correct person because you know things.

The process contains three parties (user, consumer, service) and goes as follows: 
- The user shows intent that they want to connect to the consumer via a certain service. 
- The consumer goes to get permission. 
- The user is redirected to the service provider. 
- The user gives permission, and the service generates an access token.
- The Consumer obtains an access token.
- The consumer accesses the protected resource.

## OAuth 1.0 vs. OAuth 2.0

OAuth 2.0 is a complete rewrite of OAuth 1.0 from the ground up
OAuth 2.0 is not backwards compatible with OAuth 1.0 or 1.1, and should be thought of as a completely new protocol.
OAuth 1.0 only handles web workflows, but OAuth 2.0 considers non-web clients as well.
Handling resource requests and handling user authorization can be decoupled in OAuth 2.0.
