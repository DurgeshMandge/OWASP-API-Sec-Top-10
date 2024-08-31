# Updates to the API Security Top 10
### [Introduction to OWASP API Security Top 10](https://university.apisec.ai/products/owasp-api-security-top-10-and-beyond/categories/2152491877)

### Since the release of the OWASP API Security Top 10, in 2019, API usage has grown, API-related data breaches have continued, and new API technologies have emerged. All of this has played a role in the need for an updated version of the API Security Project's Top 10 list.

### Since the 2019 Top 10, several events have demonstrated the importance of keeping the list updated and relevant. API attacks are consistently on the rise, Akamai reported seeing nearly 114 million API attacks in a single day in 2021. The global API market value was valued at $2.2 billion in 2021 and was predicted to reach $41.5 billion by 2031 (20x times growth in 10 years. In 2022, Postman had over 46 million Postman collections and Github had 3 million API-related repos. APIs continue to be rapidly adopted and the financial stakes continue to climb.  

### The OWASP API Security project updated the top ten list to address some of the changes in the attack trends that have emerged since the previous version. Inon Shkedy, OWASP API Security Project leader, stated that "The OWASP API Top 10 - 2023 version is different from the 2019 version. We aspire to follow the security trends that are relevant to APIs and have been developed in recent years. If you try to hack or protect an API that was developed 5 years ago (2018), it would make more sense to refer to the 2019 list". 

 
![alt text](/screenshots/image-1.png)

# Two Removed 
### The two items that were removed included Injection and Insufficient Logging and Monitoring. These two risks were not completely mitigated and resolved, but the importance of new emerging risks pushed them beyond the top 10. Logging and monitoring is a classic OWASP Top 10 risk but is not an item that is represented in breaches or disclosed bug bounties. Injection attacks are still around and many web APIs are still susceptible, but the adoption of web application firewalls and implementation of other mitigation techniques has reduced the occurrence of notable API injection attacks 

# Three Remain 
### There were three categories that remained on the list Broken Object Level Authorization (BOLA), Broken Function Level Authorization (BFLA), and Security Misconfiguration. BOLA and BFLA are still among the most common API risks and account for many of the breaches and bug bounty disclosures. APIs continue to have severe issues when it comes to authorization risk. The Security Misconfiguration category contains a wide range of possible misconfigurations that can plague APIs. In other words, this category is unlikely to leave the top 10 because it is a catch-all for many API vulnerabilities. 

# Four Renamed
### Four categories were renamed. The renaming of these categories helped simplify the risk categories and bring additional focus to the issue at hand. Broken User Authentication has now become Broken Authentication. This simplification has done away with "User" and now brings additional attention to API authentication as a whole process. Improper Assets Management has become Improper Inventory Management. This change was likely made to better align with industry terminology and to cover a wider range of resources. The term "assets" might only refer to tangible items valued by an organization, while the term "inventory" could refer to a wider set of resources.

# Five are New
### There were a total of five categories were added to the OWASP API Security Top 10 2023 that were not on the 2019 version. Server Side Request Forgery and Unsafe Consumption of APIs are completely new and did not have previous representation on the 2019 OWASP API Security Top 10 list. Server Side Request Forgery was represented on the 2021 OWASP Top 10 and was added to that list based on survey results rather than by incident occurrence. The remaining new risk categories include Broken Object Property Level Authorization, Unrestricted Resource Consumption, and Unrestricted Access to Sensitive Business Flows each contains elements from the 2019 list. For example, BOPLA is a combination of Excessive Data Exposure and Mass assignment. We will dive deeper into each of these later in the course.

 

# Risk Rating
### Paired with each OWASP API Security risk category are risk ratings. The risk ratings were based on the OWASP Risk Rating Methodology (Wayback Machine link). The project now refers to The OWASP Risk Rating Framework. 

![alt text](/screenshots/image.png)

### Above a table demonstrating the risk ratings used for the OWASP API Security Project from the OWASP API Security Top 10 2019 PDF. Any of these factors could significantly affect the overall likelihood of an attacker finding and exploiting a particular vulnerability. This rating does not take into account the actual impact on a specific business. The risk score must be determined by the given organization. As the project team states, "The purpose of the OWASP API Security Top 10 is not to do this risk analysis for you". In other words, the purpose of OWASP API Security Top 10 was not to perform a specific risk analysis for a given organization, but to provide a guideline for organizations to consider risk factors. 