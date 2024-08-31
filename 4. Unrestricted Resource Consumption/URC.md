# Unrestricted Resource Consumption
[API4:2023 Unrestricted Resource Consumption](https://university.apisec.ai/products/owasp-api-security-top-10-and-beyond/categories/2152492155)
## Intro
API4:2023 Unrestricted Resource Consumption is an API issue where the provider of the API does not have safeguards in place to prevent excessive use of their API. When there are no restrictions for resource consumption the API provider could become a victim of Denial of Service (DoS) attacks or experience unnecessary financial costs. Unrestricted Resource Consumption is an updated version of API4:2019 Lack of Resources and Rate Limiting.

## OWASP Attack Vector Description
Exploitation requires simple API requests. Multiple concurrent requests can be performed from a single local computer or by using cloud computing resources. Most of the automated tools available are designed to cause DoS via high loads of traffic, impacting APIs’ service rate.

## OWASP Security Weakness Description
It's common to find APIs that do not limit client interactions or resource consumption. Crafted API requests, such as those including parameters that control the number of resources to be returned and performing response status/time/length analysis should allow identification of the issue. The same is valid for batched operations. Although threat agents don't have visibility over costs impact, this can be inferred based on service providers’ (e.g. cloud provider) business/pricing model.

## OWASP Impacts Description
Exploitation can lead to DoS due to resource starvation, but it can also lead to operational costs increase such as those related to the infrastructure due to higher CPU demand, increasing cloud storage needs, etc.

The OWASP API Security Project states:</br>
**An API is vulnerable if at least one of the following limits is missing or set inappropriately (e.g. too low/high):**
* ### Execution timeouts
* ### Maximum allocable memory
* ### Maximum number of file descriptors
* ### Maximum number of processes
* ### Maximum upload file size
* ### Number of operations to perform in a single API client request (e.g. GraphQL batching)
* ### Number of records per page to return in a single request-response
* ### Third-party service providers' spending limit

# Summary
## Every API request has a technical and financial cost. When API providers do not enforce limitations on resource consumption there is an increased risk of denial of service (DoS), distributed denial of service (DDoS), unnecessary financial costs, and degradation of the quality of service to other users. In addition, rate limiting plays an important role in the monetization and availability of APIs. Many API providers monetize their APIs by limiting requests and allowing paid customers to request more information. RapidAPI, for example, allows Some API providers also have infrastructure that automatically scales with the number of requests. In these cases, an unlimited number of requests would lead to a significant and easily preventable increase in infrastructure costs.

 