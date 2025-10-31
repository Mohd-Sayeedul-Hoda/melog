---
title: DNS Records
description: Getting started with DNS records
author: sayeed
date: 2025-10-28
---

### Domain Name System also known as DNS

It basically converts the name of website that you easily understand into the IP address.
An IP address in unique number used by computer on network to identifies which  device they should communicate with.

We can check Ip address of any website on linux just by using nslookup command which mostly install on every distro

```bash
➜  melog git:(main) ✗ nslookup www.google.com
Server:         127.0.0.53
Address:        127.0.0.53#53

Non-authoritative answer:
Name:   www.google.com
Address: 142.251.222.164
Name:   www.google.com
Address: 2404:6800:4007:805::2004
```
Above we can see `142.251.222.164` (an IPv4 address) and `2404:6800:4007:805::2004` (an IPv6 address). These are the unique numerical addresses that the computer uses to know which device it has to communicate with


**Why we needed DNS** because its hard to remember above number.

### DNS Records

DNS Records are the **individual data entries within DNS** that contain information about a domain, such as its IP address, mail servers, or other configurations.
They provide the actual information needed to map a domain name to an IP address and other related data. 


I’ll discuss a few common DNS record types.
You can find the complete list here [link](https://en.wikipedia.org/wiki/List_of_DNS_record_types)


#### **A Record**
A record is a fundamental type of DNS record. It is used to point the **Domain name to its corrosponding IPv4 address**
It tells the system: 'If someone asks for example.com, send them to this specific IPv4 address

#### **AAAA Record**
AAAA record also known as quad-A records. It is used to point the **Domain name to its corresponding IPv6 address**

#### **Canonical Name Record (CNAME)**
CNAME Record is used to map any alias (different name) or subdomain to another domain. **CNAME always points to another domain name, never directly to an IP address**

Imagine you have two domain names:\
Your Nickname (The Alias): `profile.mywebsite.com` \
The Real Address (The Target): `myusername.thirdpartyservice.com` \
Instead of giving your blog's visitors the long, confusing Target address, you create an Alias (blog.mywebsite.com) that points directly to it.

#### **MX Record**
MX Records also known as Mail Exchange Records. Is use to point to mail server which will be handling mail regarding your domain.
When someone sends an email to `you@example.com`, the sending mail server checks the MX record to know exactly where to deliver it.

#### **TXT Record**
TXT Record also known as Text Record. It was first used to store text infomation inside DNS.
Now it is often used to include verification of domain ownership.

#### **NS Record**
NS Records also known as Name Server Records. It specify name servers that hold the DNS records for a particular domain.
When we type `profile.sayeedhoda.com` first it goes to Name Server where all my above records had been saved. From there
it found which Domain or IP it should point to resolve this query


**Thank you for reading!**
