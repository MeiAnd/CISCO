## Lab - Generate and Use a Digital Signature

Objectives
=   Use OpenSSL to generate a digital signature.

=   Sign a document with the digital signature.

=   Verify that a signed document has been changed.

**Background / Scenario**

A digital signature is a mathematical technique used to validate the authenticity and integrity of a digital message. The purpose of a digital signature is to prevent tampering and impersonation in digital communications. In many countries, including the United States, digital signatures have the same legal significance as traditional forms of signed documents. The United States Government now publishes electronic versions of budgets, laws, and congressional bills with digital signatures.

A digital signature algorithm consists of a signature creation and signature verification process. User A generates the digital signature and User B verifies the signature using the verification process. Both the signer and the verifier have a public and private key that they use to complete each process.

In this lab, you will use the toolkit OpenSSL to generate a digital signature. You will then generate a document, sign it with the digital signature, and then validate the authenticity and integrity of the document. Finally, you will change the document and then validate that the document is no longer authentic because its integrity has been compromised.

**.pem** = Privacy-Enhanced Mail


**Generate and view a private key.**

[analyst@secOps Desktop]$ **openssl genpkey -algorithm RSA -out private_key.pem**

- **view the private_key.pem.**

	cisco@labvm:~$ cat private_key.pem

**Generate and view a public key.**

a) To generate a public key, use the openssl pkey command. The command takes your private_key.pem as an input, and then outputs a public key (-pubout -out) to a file called public_key.pem.


**Create a new document that will be digitally signed.**

cisco@labvm:~$ echo Please transfer 2,000,000 US Dollars to Mr. Jester by 6pm today! > contract.txt

**Use the private key to digitally sign the new document.**

**A.** To sign the document, use the openssl dgst command. The dgst command can take any number of message digest values. In this example, you will use SHA 256, and then use private_key.pem to output a signature for the contract.txt document.

cisco@labvm:~$ **openssl dgst -sha256 -sign private_key.pem -out signature contract.txt**


**Part 6: Verify the authenticity and integrity of the document.**

Digital signature technology allows the recipient to verify the file’s authenticity and integrity. The process of digital signature verification is to ensure that a given message has been signed by the private key that corresponds to a given public key.

To verify that the document is authentic and has not been tampered with, use the openssl dgst command with the verify option and the public_key.pem.

cisco@labvm:~ openssl dgst -sha256 -verify public_key.pem -signature signature contract.txt

Verified OK


**Simulate a threat actor changing the specified recipient in the contract.txt file.**


a.Use gedit to open the contract.txt file.**
cisco@labvm:~$ gedit contract.txt

b. Change Mr. Jester to Mr. Viper.

c. Save


**Part 8: Verify that the document's integrity has been compromised.**

cisco@labvm:~ **openssl dgst -sha256 -verify public_key.pem -signature signature contract.txt**

Verification Failure


