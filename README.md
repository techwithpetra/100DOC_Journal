# 100 Days of Code Journal 

Revised date
### Duration: Monday 25th August 2025 - Wednesday 3rd December 2025

Journal to document 100 doc journey 
 Day 1: 1/09/2025 
 - Setup Github and Dev Accounts and learn about ssh and refresh memory on git intitialisation commands
 - I also researched into SSL certificates. Figuring out a way to add a free ssl certificate for a website in hosted with LDN
 - Discovered that they may be a way using cloudflare but in the lcn host they need to disable DNSSEC
 - DNSSEC is a cryptographic signature that allows the signatures to be registered with the DNS registered on the host
 - Cloudflare needs the dns domain to disable it so that when the namespace is changes to its own there are no clashes
 - LCN doesn't provide a self-service for the user to directly update this so i created a support ticket and hopefully this can be disabled to continue with the progress of that work
 - Also started AI & Machine learning course - learnt what machine learning is 

Day 2: 2/09/2025 
- Gone through web development training course
- Continued to work on Praying Promises website

Day 3: 3/09/2025
- Continued on web development courses
- Learnt about nameservers
- Nameservers is what DNS Systems use to translate FQDN to IP address
- I added cloudflares nameservers to where a client website is hosted.
- However LCN is inflexible and doesn't provide an interface to upload the SSL certificate and private key generated
- Cloudflare on its SSL services has modes of encryption i initially chose full strict mode but the handshake failed due to their being no SSL cert
- However they have a flexible mode where cloudflare handles encryption of webtraffic from web browsers to its servers but onwards its not encrypted. The advantage of this is that it encrypts messages to its servers so it provides some level of protection and also is a way to get around the web browser showing that the website is not encrypted. However the disadvantage is its not e2e encrypted from the cloudflare servers to where your website is being hosted. That part the web traffic is still http than https. 

Day 4: 4/09/2025
- Created landing page for Praying promise
- Continued on web development course 

