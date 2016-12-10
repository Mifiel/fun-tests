# Change password of the FIEL with JS (or node)


## Context

The FIEL (e.firma) is part of a PKI (Public Key Infrastructure) 
developed by the Mexican government to allow citizens to securely 
authenticate their identity online and sign documents electronically. 
It is issued by the SAT and, at the moment, is primarily used to sign tax returns online. 
However, Mexican law allows the FIEL to be used to sign ANY legal document --such as contracts, 
invoices and more-- with the same validity as an autograph signature.

## Problem

The majority of people don’t understand what the FIEL is and the power this tool holds. 
This leads them to set weak, and therefore insecure passwords. If a FIEL with an 
insecure password is stolen, it is relatively easy to brute force it. This would allow 
the thieves to steal the identity of the legal owner and sign documents on their behalf, 
which can cause a lot of harm to the owner of the FIEL.

## Objective

Build a small web app that allows a user (that now understands the power of his FIEL) 
to change the password of the private key in an easy and intuitive way. It is assumed 
that the owner of the FIEL knows his original password.

## Test

Develop a web application or a js library (can be nodejs) that accepts a private key, 
its original password and a new password of the user’s choice, then returns a new private 
key (it can be `PEM` or `DER` encoded).


## Notes

- There is no time limit to deliver the solution but the speed will be taken into account.
- There are not many js libraries that use RSA algorithms. If you’re having trouble finding one, 
please do reach out and we will happily provide one.
- We encourage you to communicate as much as you can, so please don’t be afraid of asking questions. 
Remember, there is no such thing as a dumb question!
- The private key of the FIEL is in `PKCS7` format, the input and output private key should have this format.
- The password of the provided key (FIEL_AAA010101AAA.key) is **12345678a**

**Good luck!!**
