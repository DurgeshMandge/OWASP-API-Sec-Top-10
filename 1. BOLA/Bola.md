# BOLA
### [API1:2023 Broken Object Level Authorization](https://university.apisec.ai/products/owasp-api-security-top-10-and-beyond/categories/2152491878)
## Intro
#### API1:2023 Broken Object Level Authorization (BOLA) is one of the most prevalent and severe vulnerabilities for APIs. BOLA vulnerabilities occur when an API provider does not have sufficient controls in place to enforce authorization. In other words, API users should only have access to sensitive resources that belong to them. When BOLA is present an attacker will be able to access the sensitive data of other users. 

## OWASP Attack Vector Description
#### Attackers can exploit API endpoints that are vulnerable to broken object-level authorization by manipulating the ID of an object that is sent within the request. Object IDs can be anything from sequential integers, UUIDs, or generic strings. Regardless of the data type, they are easy to identify in the request target (path or query string parameters), request headers, or even as part of the request payload.

 

## OWASP Security Weakness Description
#### This has been the most common and impactful attack on APIs. Authorization and access control mechanisms in modern applications are complex and widespread. Even if the application implements a proper infrastructure for authorization checks, developers might forget to use these checks before accessing a sensitive object. Access control detection is not typically amenable to automated static or dynamic testing.

 

## OWASP Impacts Description
#### Unauthorized access can result in data disclosure to unauthorized parties, data loss, or data manipulation. Unauthorized access to objects can also lead to full account takeover.

 

# Summary
#### If an API endpoint does not have sufficient access controls, it will not perform checks to make sure users can only access their own resources.</br> When these controls are missing, User A will be able to obtain User B’s resources via API requests.
#### APIs use some sort of value, like names or numbers, to identify various objects.</br> When an attacker discovers an API's resource IDs, they will attempt to obtain the resources when unauthenticated or authenticated as a different user.</br> For instance, imagine that an authenticated user, Bruce, sends a GET request to https://herohospital.com/api/v3/users?id=2727 and receives the following response:

{
"id": "2727", </br>
"fname": "Bruce",</br>
"lname": "Wayne",</br>
 "dob": "1975-02-19",</br>
"username": "bman",</br>
"diagnosis": "Depression",</br>
}

#### This poses no problem; Bruce should be able to access Bruce's own information.</br> However, if Bruce is able to access another user’s information then a BOLA vulnerability would be present.</br> A weakness can be tested by using other resource IDs in place of 2727. Say Bruce is able to obtain information about another user by sending a request for https://herohospital.com/api/v3/users?id=2728 and receives the following response:

{
"id": "2728",</br>
"fname": "Harvey",</br>
"lname": "Dent",</br>
 "dob": "1979-03-30",</br>
"username": "twoface",</br>
"diagnosis": "Dissociative Identity Disorder",</br>
}

#### Assuming that Bruce is still using his authorization to access this data, this would be a clear indication that the API is vulnerable to BOLA. 

#### BOLA isn't always as simple as this example because there is flexibility in how resources are provisioned and requested from one API to the next. Below are a few examples of how different resources may be accessed via API requests.</br> 

### The bold resource IDs in the following API requests should catch your attention:

* GET /api/user/1</br>
* GET /user/account/find?user_id=aE1230000token</br>
* POST /company/account/Apple/balance</br>
* GET /admin/settings/account/bman</br>

### In these instances, you can probably guess other potential resources, like the following, by altering the bold values:

* GET /api/resource/3</br>
* GET /user/account/find?user_id=23</br>
* POST /company/account/Google/balance</br>
* POST /admin/settings/account/hdent</br>
  

#### In these examples, tests can be performed by replacing the bolded resource IDs with other numbers or words. (Of course, in POST requests the resource could also be requested in the POST body). If a UserA can successfully access the information of any other user then there is a vulnerability present. BOLA vulnerabilities are the most common API vulnerability, are easily exploitable, and require a low amount of technical skills to discover. </br>BOLA can present itself in many forms depending on how resources are organized. As you can see in this table, resources can be organized by user, by group, or by a combination of both. In all of these instances, only those with the proper permissions should be allowed to retrieve their resources.

![alt text](/screenshots/Bola.png)

 

# OWASP Preventative Measures
#### In order to improve API security, it is important to implement robust authorization controls. These controls should consider user policies and role-based access control hierarchies. The primary focus should be to ensure that authenticated users only have access to resources they are authorized to have access to. Using less predictable resource IDs can increase the challenge of a user or attacker guessing the resource IDs of other users. Developers should perform tests that specifically test authorization controls. 

### Implement a proper authorization mechanism that relies on the user policies and hierarchy.
#### Use the authorization mechanism to check if the logged-in user has access to perform the requested action on the record in every function that uses an input from the client to access a record in the database.
### Prefer the use of random and unpredictable values as GUIDs for records' IDs.
Write tests to evaluate the vulnerability of the authorization mechanism. Do not deploy changes that make the tests fail.