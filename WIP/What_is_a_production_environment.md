# What is a production environment

## ✅ Checkpoints

- It is hosted on an environment that is paid or provided by the client (e.g Client IT team servers, OVH or AWS VMs).
  - The client must be able to administrate his production after the leave of M33.
- The server is managed by the client IT team or a specialized company (e.g Synalabs).
  - Someone, other than M33, must be in charge of restarting the application if it falls at 3 a.m.
- I have a plan to absorb the application expected load (Server RAM, CPU and SSD, load balancing, limiter...).
- It has a DNS entry on a domain administrated by the client.
- It has an SSL certificate installed and a system to renew it periodically (e.g Let's Encrypt).

If at the technical challenge, those conditions can't be met, the architect must send an email to the client with :

- The Project Director in copy.
- All the OK/NOK items.
- His recommendations.
- He must have in response the formal agreement of the client to start the project despite those NOK points. 

## Examples

### BPI - PME project

The client wanted to develop a POC during 4 weeks. The BPI IT needed 3-6 months to deliver a production environment. During the technical challenge, to gain time Georges choose to host the production on the Theodo OpenStack. **This was a bad practice :**

- ❌ Hosting paid or provided by the client.
- ❌ Managed server.
- ✅ Plan to absorb the load.
- ❌ DNS entry administrated by the client.
- ✅ SSL certificate renewed periodically.

### Fast IT projects

At Fast IT, the specifications of the servers is sent to an internal IT Team that delivers them with a DNS and an SSL certificate. 

After the servers have been delivered, two Fast IT OPs manage the servers.

- ✅ Hosting paid or provided by the client.
- ✅ Managed server.
- ✅ Plan to absorb the load.
- ✅ DNS entry administrated by the client.
- ✅ SSL certificate renewed periodically.
