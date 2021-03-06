---
linkTitle: "MFA Faq"
date: 2017-01-05
weight: 1
---

#### **What will need to have MFA authentication?** 

MFA is requirement for ALL authentication point in the system. This generally includes:

- MFA for cloud console access such as AWS and GCP console ([Recommened Solution](https://gohugo.io))
- MFA for remote access of EC2 instances and appliances such as RDP and SSH ([Recommened Solution](https://gohugo.io))
- MFA for web application, web portals etc . ([Recommened Solution](https://gohugo.io))

**Note:** Multi-factor authentication (MFA) method should aligns with the Digital Identity Acceptance Statement and NIST 800-63 part B. NIST is encouraging the use of a secure method that does not expose the MFA pin to intercept risk. 

 Acceptable MFA solution
- PIV
- PIV derived (SAML, OIDC, OAUTH)
- TOTP (e.g., Google Authenticator, Authy)
- HOTP (physical token)
- SMS to registered phone numbers

 Not Acceptable MFA Solution
 - MFA token sent via email


#### **Can you give some example of MFA implementation for GSA DevSecOps Teams?**

MFA For AWS console access  

- AWS native MFA using AWS IAM and virtual MFA device by installing Google Authenticator or Authy app on GSA provided mobile phone.
- MFA using federation using ADFS or OpenAM. FCS uses openam based federation and FCS tenant inherit this by default

MFA for remote access of EC2

- Controlled access to EC2 instance (SSH, RDP, Web Access etc) through GSA hosted admin VDI, which requires short name token.Access to (SSH, RDP, Web Access etc) should be allowed through only admin VDI.
-  Build your own jump server in your environment which requires two factor authentication . This jump server is only entry point to your environment for any remote access. ( Note: We are looking for automation code that building jump server. which forces two factor authentication using piv card or sna token cert etc) 



#### **Can i get example of bla bla code?**

Below is example code

```
foo := "bar";
bar := "foo";
```

####  **Can i get git link for example code?** 


| Example   | Git links       |
|-----------|-----------------|
| A table   | A header        |
| A table   | A header        |
| A table   | A header        |