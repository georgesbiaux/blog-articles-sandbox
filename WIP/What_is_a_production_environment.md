# What is a production environment

## ✅ Checkpoints

- It is hosted on an environment that is paid or provided by the client (e.g Client IT team servers, OVH or AWS VMs).
  - The client must be able to administrate his production after the leave of M33.
- The server is managed by the client IT team or a specialized company (e.g Synalabs).
- The server specifications (RAM, CPU, SSD) match the expected load of the application.
- It has a DNS entry on a domain administrated by the client.
- It has an SSL certificate installed and a system to renew it periodically (e.g Let's Encrypt).

## Examples

### BPI - PME project

The client wanted to develop a POC during 4 weeks. The BPI IT needed 3-6 months to deliver a production environment. During the technical challenge, to gain time Georges choose to host the production on the Theodo OpenStack :

- ❌ It is hosted on an environment that is paid or provided by the client (e.g Client IT team servers, OVH or AWS VMs).
- ❌ The server is managed by the client IT team or a specialized company (e.g Synalabs).
- ✅ The server specifications (RAM, CPU, SSD) match the expected load of the application.
- ❌ It has a DNS entry on a domain administrated by the client.
- ✅ It has an SSL certificate installed and a system to renew it periodically (e.g Let's Encrypt).

### Fast IT projects

At Fast IT, the specifications of the servers is sent to an internal IT Team that delivers them with a DNS and an SSL certificate. 

After the servers have been delivered, two Fast IT OPs manage the servers.

- ✅ It is hosted on an environment that is paid or provided by the client (e.g Client IT team servers, OVH or AWS VMs).
- ✅ The server is managed by the client IT team or a specialized company (e.g Synalabs).
- ✅ The server specifications (RAM, CPU, SSD) match the expected load of the application.
- ✅ It has a DNS entry on a domain administrated by the client.
- ✅ It has an SSL certificate installed and a system to renew it periodically (e.g Let's Encrypt).
