# CA Certificate Authority

![Project Screenshot](./images/test.jpg)

If you ever tried going to a website you've probably seen this lock
ever wondered how it works?

### How websites prove they’re legit?
Our internet depends on encryption to protect our sensitive data from cyber attacks (phishing, spoofing, hacking). Without a way to verify the identity of a website, attackers could easily replicate a real website, tricking unsuspecting users into handing over their credentials or other sensitive information.

This is the problem that a Certificate Authority (CA) solves, by validating website ownership and issuing TLS/SSL certificates.
"NOTE: TLS and SSL can be used changeably TLS is a modern version of SSL"
	
CA enables encryption between the browser (user) and the server. This encryption ensures that the data exchanged remains secure. Without a CA, online banking, shopping, and social media would be very risky to visit, as there would be no reliable way to verify a genuine website.

Keep in mind though, that just because a website has a certificate doesn't automatically mean it's secure. Hackers can still obtain **Domain Validated (DV) certificates** for fake websites. That's why businesses handling sensitive transactions often opt for **Organization Validated (OV) certificates** or **Extended Validation (EV) certificates**, which provide more validity.

### How CA's Validate client?
CA is the one who is responsible for giving websites a certificate so users can tell if they are legit 

Certificate Authrotiy (CA) are verified organizations like , LetsEncrpyt Digicert, GlobalSign, SSL Store, Before a CA issues a certificate they verify important details about requester

- DV certificates, the CA verifies that the applicant has control over the domain,  ( for personal websites )
- OV certificates, the CA confirms the organization's identity by referencing official government records.  (Commonly used for business and public-facing websites.)
- EV certificates, the CA conducts the most thorough validation process to ensure the business is legitimate. (High security websites like online banking, ecommerrce, goverment)

DV, OV, EV are types of SSL / TLS certificates note that there are other types of digital certificate issued by CA's like which we wont go deep dive into but here are some examples

- Device Certificates
- Code Signing Certificates
- Email Certificate
- Root Certificates
- **Self Signed Certificates**: not trusted by browser will and is typically used for testing or internal purpose

all of these fall under the umbrella of PKI certificates (more on pki later)

##### Public and Private CA
so far we've been talking about public CA but what is private CA when a company needs a secure internal system it may face challenge of managing ssl certificate. Using a Private Certificate (CA) the company can issue certificates trusted within its network only this is needed so the systems wont get flagged by the browser remember that browser has a built system for checking certificate so if the website doesnt have it will be shown as insecure


##### Certificates and Cloud Providers
Cloud providers offer tools for managing ssl/tls certificates like, automatic requesting for your domain names, automatic renewal of publicly issued certificate  and it easy integrates with other resource like load balancer, Global CDN and service of cloud providers and services within the cloud platform:

- **AWS**: AWS Certificate Manager (ACM)
- **Azure**: Azure Key Vault (Certificate Management)
- **Google Cloud**: Google Cloud Certificate Manager

Lastly, it's important to remember that CA certificates expire and must be renewed to remain trusted by clients. Renewing a CA certificate is usually pretty straightforward just submit another Certificate Signing Request (CSR) and update your certificate.

And as always, we’re just scratching the surface, there's a lot more to learn in Certificates

Here are some questions you could ponder upon or dive into yourself
- How the end to end flow works from a server’s certificate issuance to browser retrieval and validation?
- TLS vs SSL: What's the difference? (Deep Dive)
- What is Certificate Chain? 

But that's the end for this blog, see ya on another blog and thanks for reading : )


### Index
CA = Certificate Authority
Certificate = 
	contains things like, domain name, orgname, public key, issuer, expiration
TLS/SSL Certificate = 
Certificate Signing Request (CSR) = just a base 64 encoded with information about your identity, you genereate this by (GET BACK TO THIS)
