![Alt text](https://www.cloudflare.com/img/learning/security/glossary/what-is-ssl/http-vs-https.svg)

## What is SSL/TLS?
<b>SSL</b>, or Secure Sockets Layer, is an encryption-based Internet security protocol. It was first developed by Netscape in 1995 for 
the purpose of ensuring privacy, authentication, and data integrity in Internet communications. SSL is the predecessor to the modern TLS encryption used today.

<b>TLS</b>,Transport Layer Security, or TLS, is a widely adopted security protocol designed to facilitate privacy and data security for 
communications over the Internet. TLS  used to encrypt other communications such as email, messaging, and voice over IP (VoIP).

### Are SSL and TLS the same thing?
SSL is the direct predecessor of another protocol called TLS (Transport Layer Security).
The differences between the final version of SSL (3.0) and the first version of TLS are not drastic; the name change was applied to signify the change in ownership.

![Alt text](https://res.cloudinary.com/practicaldev/image/fetch/s--SfAucjE3--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/0lb1buik85z6dkrn274b.png)

### How does SSL/TLS work?

- <b>Encryption</b>: hides the data being transferred from third parties.

- <b>Authentication</b>: ensures that the parties exchanging information are who they claim to be, This process called [handshake](https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/) .

- <b>Integrity</b>: verifies that the data has not been forged or tampered with.



### Why is SSL/TLS important?
Originally, data on the Web was transmitted in plaintext that anyone could read if they intercepted the message. For example, if a consumer visited a shopping website, placed an order, and entered their credit card number on the website, that credit card number would travel across the Internet unconcealed.

SSL was created to correct this problem and protect user privacy. By encrypting any data that goes between a user and a web server, SSL ensures that anyone who intercepts the data can only see a scrambled mess of characters. The consumer's credit card number is now safe, only visible to the shopping website where they entered it.

SSL also stops certain kinds of cyber attacks: It authenticates web servers, which is important because attackers will often try to set up fake websites to trick users and steal data. It also prevents attackers from tampering with data in transit, like a tamper-proof seal on a medicine container.








## What is an SSL certificate?

SSL certificates are what enable websites to move from HTTP to HTTPS, which is more secure. An SSL certificate is a data file hosted in a website's origin server. SSL certificates make SSL/TLS encryption possible, and they contain the website's public key and the website's identity, along with related information. Devices attempting to communicate with the origin server will reference this file to obtain the public key and verify the server's identity. The private key is kept secret and secure.

## What information does an SSL certificate contain?

- The domain name that the certificate was issued for
- Which person, organization, or device it was issued to
- Which certificate authority issued it
- The certificate authority's digital signature
- Associated subdomains
- Issue date of the certificate
- Expiration date of the certificate
- The public key (the private key is kept secret)

## How to generate and use an SSL certificate in NodeJS?

supposed that you are create express app.
```
mkdir cert
cd cert
```

To generate the SSL Certificate we need to follow these steps as shown below:

#### Generate a Private Key
```
 openssl genrsa -out key.pem
```
Once we ran the above command it will generate the private key and save it in key.pem file inside cert directory and gives this type of message in the terminal.
```
Generating RSA private key, 2048 bit long modulus
...+++
.................+++
e is 65537 (0x10001)

```

#### Create a CSR ( certificate signing request) using the private key.

we need to use CSR to generate our certificate. To do so we need to run the below command.
```
openssl req -new -key key.pem -out csr.pem
```
Once we ran this command it will ask a few questions as shown below

#### Generate the SSL certification from CSR

Now for the final steps, we need to use the key.pem and crs.pem files to generate our SSL certificate.
```
openssl x509 -req -days 365 -in csr.pem -signkey key.pem -out cert.pem
```
### Integration of the SSL Certificate in Express
Now let's in index.js file after app, let us add this:
```
const options ={
  key:fs.readFileSync(path.join(__dirname,'./certs/key.pem')),
  cert:fs.readFileSync(path.join(__dirname,'./certs/cert.pem')) 
}
const sslserver =https.createServer(options,app)
```
Once it's done save it and run the server.
```
https://localhost:3002
```
