# Two Factor Authentication


### How does Google Authenticator work?

[Answers](https://security.stackexchange.com/questions/35157/how-does-google-authenticator-work) on StackOverflow:

@user10211

> Google Authenticator supports both the HOTP and TOTP algorithms for generating one-time passwords.

> With HOTP, the server and client share a secret value and a counter, which are used to compute a one time password independently on both sides. Whenever a password is generated and used, the counter is incremented on both sides, allowing the server and client to remain in sync.

> TOTP essentially uses the same algorithm as HOTP with one major difference. The counter used in TOTP is replaced by the current time. The client and server remain in sync as long as the system times remain the same. This can be done by using the Network Time protocol.

---



**Time-Based One-Time Password (TOTP)** algorithm. It has the following ingredients:

• A shared secret (a sequence of bytes)

• An input derived from the current time

• A signing function

-@Arjun SK


**HMAC-based One-time Password algorithm (HOTP)** is a one-time password (OTP) algorithm based on hash-based message authentication codes (HMAC). It is a cornerstone of the Initiative for Open Authentication (OATH).
-Wikipedia
