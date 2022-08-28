# Stateless vs Stateful Authentication

## Session Based Authentication

In the session based authentication, the server will create a session for the user after the user logs in. The session id is then stored on a cookie on the user’s browser. While the user stays logged in, the cookie would be sent along with every subsequent request. The server can then compare the session id stored on the cookie against the session information stored in the memory to verify user’s identity and sends response with the corresponding state!

![alt text](https://miro.medium.com/max/1400/1*Hg1gUTXN5E3Nrku0jWCRow.png)

## Advantages

- Revoke the session anytime
- Easy to implement and manage for one-session-sever scenario
- Session data can be changed later (assume that for a one-session-sever, no inconsistent problem)

## Disadvantages

- Increasing server overhead: As the number of logged-in users increases, the more server resources are occupied.
- Fail to scale
- Difficult for 3rd party applications to use your credentials

## Token Based Authentication

Many web applications use JSON Web Token (JWT) instead of sessions for authentication. In the token based application, the server creates JWT with a secret and sends the JWT to the client. The client stores the JWT (usually in local storage) and includes JWT in the header with every request. The server would then validate the JWT with every request from the client and sends response.

![alt text](https://miro.medium.com/max/1400/1*PDry-Wb8JRquwnikIbJOJQ.png)

## Advantages

- Lower server overhead
- Easy to scale
- Good to integrate with 3rd party application

## Disadvantages

- Cannot revoke the session anytime.
- Relatively complex to implement for one-session-server scenario
- Session data cannot be changed until its expiration time
