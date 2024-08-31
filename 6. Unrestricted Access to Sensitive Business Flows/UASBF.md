# Unrestricted Access to Sensitive Business Flows
[API6:2023 Unrestricted Access to Sensitive Business Flows](https://university.apisec.ai/products/owasp-api-security-top-10-and-beyond/categories/2152492181)
## Intro
API6:2023 Unrestricted Access to Sensitive Business Flows represents the risk of an attacker being able to identify and exploit API-driven workflows. If vulnerable an attacker will be able to leverage an organization's API request structure to obstruct other users. This obstruction could come in the form of spamming other users, depleting the stock of highly sought-after items, or preventing other users from using expected application functionality. This is a new addition to the 2023 top ten list.

 

## OWASP Attack Vector Description
Exploitation usually involves understanding the business model backed by the API, finding sensitive business flows, and automating access to these flows, causing harm to the business.

 

## OWASP Security Weakness Description
Lack of a holistic view of the API in order to fully support business requirements tends to contribute to the prevalence of this issue. Attackers manually identify what resources (e.g. endpoints) are involved in the target workflow and how they work together. If mitigation mechanisms are already in place, attackers need to find a way to bypass them.

 

## OWASP Impacts Description
In general technical impact is not expected. Exploitation might hurt the business in different ways, for example: prevent legitimate users from purchasing a product, or lead to inflation in the internal economy of a game.

 

# Summary
Regarding APIs, a flow is a series of requests and responses that lead to an operation. If, for example, a purchase flow for a web application does not restrict access to a purchase process then a scalper could automate requests to instantly drain the stock of an item down to nothing. This is where mechanisms like a Completely Automated Public Turing test to tell Computers and Humans Apart or CAPTCHA comes into play. If a flow has a CAPTCHA mechanism that requires human interaction then the automated requests could be interrupted and slow down automated purchasing.

![alt text](/screenshots/uabsd.png)

# OWASP Preventative Measures
## The mitigation planning should be done in two layers:
1. Business - identify the business flows that might harm the business if they are excessively used.
2. Engineering - choose the right protection mechanisms to mitigate the business risk.</br>
*Some of the protection mechanisms are more simple while others are more difficult to implement.</br> 
The following methods are used to slow down automated threats:*

* ### Device fingerprinting: denying service to unexpected client devices (e.g headless browsers) tends to make threat actors use more sophisticated solutions, thus more costly for them
* ### Human detection: using either captcha or more advanced biometric solutions (e.g. typing patterns)
* ### Non-human patterns: analyze the user flow to detect non-human patterns (e.g. the user accessed the "add to cart" and "complete purchase" functions in less than one second)
* ### Consider blocking IP addresses of Tor exit nodes and well-known proxies
Secure and limit access to APIs that are consumed directly by machines (such as developer and B2B APIs). They tend to be an easy target for attackers because they often don't implement all the required protection mechanisms.