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

## Why do websites need an SSL certificate?

- Encryption: SSL/TLS encryption is possible because of the public-private key pairing that SSL certificates facilitate. Clients (such as web browsers) get the public key necessary to open a TLS connection from a server's SSL certificate.

- Authentication: SSL certificates verify that a client is talking to the correct server that actually owns the domain. This helps prevent domain spoofing and other kinds of attacks.

- HTTPS: Most crucially for businesses, an SSL certificate is necessary for an HTTPS web address. HTTPS is the secure form of HTTP, and HTTPS websites are websites that have their traffic encrypted by SSL/TLS.

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
