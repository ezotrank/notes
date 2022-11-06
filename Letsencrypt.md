# Letsencrypt

tags: letsencrypt

## Challenges

**HTTP-01 challenge**

Let’s Encrypt gives a token to your ACME client, and your ACME client puts a file on your web server at http://<YOUR_DOMAIN>/.well-known/acme-challenge/<TOKEN>. That file contains the token, plus a thumbprint of your account key.

Pros:

- It’s easy to automate without extra knowledge about a domain’s configuration.
- It allows hosting providers to issue certificates for domains CNAMEd to them.
- It works with off-the-shelf web servers.

Cons:

- It doesn’t work if your ISP blocks port 80 (this is rare, but some residential ISPs do this).
- Let’s Encrypt doesn’t let you use this challenge to issue wildcard certificates.
- If you have multiple web servers, you have to make sure the file is available on all of them.

**DNS-01 challenge**

This challenge asks you to prove that you control the DNS for your domain name by putting a specific value in a TXT record under that domain name.
After Let’s Encrypt gives your ACME client a token, your client will create a TXT record derived from that token and your account key, and put that record at _acme-challenge.<YOUR_DOMAIN>.

Pros:

- You can use this challenge to issue certificates containing wildcard domain names.
- It works well even if you have multiple web servers.

Cons:

- Keeping API credentials on your web server is risky.
- Your DNS provider might not offer an API.
- Your DNS API may not provide information on propagation times.

**Get more info about the certificate**

`echo | openssl s_client -showcerts -servername test1.example.com -connect test1.example.com:443 2>/dev/null | openssl x509 -inform pem -noout -text`

**Rate limits**

- The main limit is Certificates per Registered Domain (50 per week). A registered domain is, generally speaking, the part of the domain you purchased from your domain name registrar. For instance, in the name www.example.com, the registered domain is example.com. In new.blog.example.co.uk, the registered domain is example.co.uk.

**Find cert by domains**

https://crt.sh