---
title: "Review. CryptDB - Processing Queries on an Encrypted Database"
date: 2018-10-14T04:56:39-07:00
draft: false
---


#### Paper: CryptDB - Processing Queries on an Encrypted Database
##### by Raluca Ada Popa, Catherine M.S. Redfield, Nickolai Zeldovich, and Hari Balakrishnan


The paper proposed the use of encrypted Database server where none of the data is stored in plain text. The paper initially describes the problems that occur due to passive DB server attacks when the System Administrators have access to confidential information and such threat models. CryptDB is ideal to be used in cases of passive database server attacks. The goal of CryptDB is to protect data confidentiality by enabling a server to 'compute over encrypted data'. 

The Paper views two threat models and explains how the use of CryptDB mitigates the threat. To implement CryptDB in the existing application or database server, no changes need to be made since it is portable and contains SQL query interface.CryptDB uses SQL aware encryption and adjustable query based encryption. It uses onion encryptions layers. CryptDB uses SQL-aware encryptions for limited operators. The encryption methods used are RND, DET, OPE, HOM, JOIN, and SEARCH. These methods are used as the operators for SQL. The onion encryption layers have various levels of these security included by the use of the RND, SEARCH, and HOM is the outer layers. CryptDB also used a proxy server which used to encrypt the database server. The figure 3(a) clearly explains the process of CryptDB. The SQL query is processed in the CryptDB proxy which uses the onion structure for processing each portion of the query. The leading paper also proposes the idea of key chaining where the user passwords are chained together. This concept protects the inactive users or users who have not logged onto the machine at the time of the attack of the database server. This can prevent data leakage when the system is compromised. The concept of anonymizing the data columns along with the data is an exciting concept. The CrypotDB server has low-performance overhead according to the TPC-C benchmark.


The analysis of CryptDB is the concept of encrypting the database and processing the queries is a better approach which helps to establish data confidentiality. The implementation is fast, and it is scalable which means it feasible to deploy. The concept of using proxy onion encryption also ensured secure access to the data. 

While researching more about CryptDB and its implementations, I came across the Microsoft Research which points out the threat model in CryptDB. Using Frequency Analysis, the research was able to find out the frequency of characters within the text and the match was found against comparison with DTE encrypted data columns. 

The other attacks on CryptDB are:
- Lp-optimizations
- Sorting attacks
- and cumulative attacks. 

The CryptDB has explained the attacks in the paper titled `CryptDB: Protecting Confidentiality with Encrypted Query Processing`  mentions 'correctly use the order encryption scheme (for the right types of data), or do not use it.'. This is relevant since it prevents database administrators from snooping and ensured data confidentiality.The idea of setting up a proxy to secure the database server and the application server is a novel idea. I think the concept of onion layering or union of encryption layers is an excellent approach to minimize data leakage.CryptDB also protects the user who is not logged into the application by using keychain of the user passwords so that data is encrypted with access privileges.The validations of CryptDB is limited. The data of the user who are logged into the server is at risk when the database is compromised which is not a good design approach. The computation of layers of encryption creates a low performance. This approach cannot be used for fast-paced data retrieval processes. I have the opinion that CryptDB is a feasible solution for the problem of data breaches. The operators supported in this proxy server is limited.


Since CryptDB compromises the data of the users who have logged into the machine,is this a good approach for a database server? After reviewing the paper, there are many concepts of CryptDB which aren't covered in the paper. There can be various other threat models where the database administrator can access the web application through which he can insert malicious code into the rows. He can also change the database privileges. The paper does not talk about the web application based attack models. It was not clear how CryptDB would handle the overhead if the database had multiple copies of all columns and a large number of onions. As mentioned in the paper,CryptDB supports only limited operations. If the existing application had queries which used queries which isn't supported by the CryptDB, then how would the CryptDB proxy be set up in such cases. The paper mentioned that the all the data in DB is secured by the keychain along with the user's key. The mechanism of keychain was not precise but if the user's key has been compromised and new key generated, how does the CryptDB modify the keychain according to the new key. What is the overhead during such incidents?

