# Access Control (ACL)

1. When is Basic Authorization used vs. Bearer Authorization?

   The Basic and Digest authentication schemes are dedicated to the authentication using a username and a secret
   The Bearer authentication scheme is dedicated to the authentication using a token. Even if this scheme comes from an OAuth2 specification, you can still use it in any other context where tokens are exchange between a client and a server. Concerning the JWT authentication and as it is a token, the best choice is the Bearer authentication scheme. Nevertheless, nothing prevent you from using a custom scheme that could fit on your requirements.

2. What does the JSON Web Token package do?

   defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

3. What considerations should we make when creating and storing a SECRET?

   Secrets that you create in Secrets Manager can be static or dynamic in nature. A static secret has its expiration date and time enforced at secret creation or rotation time. In contrast, a dynamic secret has its expiration date and time enforced when its secret data is read or accessed.

## Term:

- encryption
  the method by which information is converted into secret code that hides the information's true meaning. The science of encrypting and decrypting information is called cryptography. In computing, unencrypted data is also known as plaintext, and encrypted data is called ciphertext.

- token
  is a piece of a two-factor authentication security device that may be used to authorize the use of computer services. Software tokens are stored on a general-purpose electronic device such as a desktop computer, laptop, PDA, or mobile phone and can be duplicated.

- bearer
  The Bearer authentication scheme is dedicated to the authentication using a token. Even if this scheme comes from an OAuth2 specification, you can still use it in any other context where tokens are exchange between a client and a server. Concerning the JWT authentication and as it is a token, the best choice is the Bearer authentication scheme. Nevertheless, nothing prevent you from using a custom scheme that could fit on your requirements.

- secret
  Secrets that you create in Secrets Manager can be static or dynamic in nature. A static secret has its expiration date and time enforced at secret creation or rotation time. In contrast, a dynamic secret has its expiration date and time enforced when its secret data is read or accessed.

- JSON Web Token
  defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

## Preparation Materials:

**Role Based Access Control**:
**RBAC** is nothing more than the idea of assigning system access to users based on their role within an organization. The system needs of a given workforce are analyzed, with users grouped into roles based on common job responsibilities and system access needs. Access is then assigned to each person based strictly on their role assignment. With tight adherence to access requirements established for each role, access management becomes much easier.

**Benefits of RBAC**
With RBAC, access management is easier as long as you adhere strictly to the role requirements. RBAC helps you:

- create systematic, repeatable assignment of permissions
- easily audit user privileges and correct identified issues
- quickly add and change roles, as well as implement them across APIs
- cut down on the potential for error when assigning user permissions
- integrate third-party users by giving them pre-defined roles
- more effectively comply with regulatory and statutory requirements for confidentiality and privacy

**Role-based access control in Auth0**
Currently, we provide two ways of implementing role-based access control (RBAC), which you can use in place of or in combination with your API's own internal access control system:

- Authorization Core
- Authorization Extension

We are expanding our Authorization Core feature set to match the functionality of the Authorization Extension. Our new core RBAC implementation improves performance and scalability and will eventually provide a more flexible RBAC system than the Authorization Extension.

**more resources:**
[RBAC tutorial](https://www.youtube.com/watch?v=C4NP8Eon3cA) /
[5 steps to RBAC](https://www.csoonline.com/article/3060780/5-steps-to-simple-role-based-access-control.html) /
[wiki - RBAC](https://en.wikipedia.org/wiki/Role-based_access_control)
