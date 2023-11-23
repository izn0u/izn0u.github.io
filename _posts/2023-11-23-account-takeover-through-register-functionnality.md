## Account takeover through register functionnality

In this post i'm going to share a vulnerability i found on several target using java.

### Summary
it was possible to takeover any acccount on redacted.com knowing only the email using the registering functionnality. Adding `\u0023` (#) at the end of the email (victim@test.com\u0023) we can register a already existing account with different password.

### Steps To Reproduce:
1.create an account (victim@test.com) 
2.go to the account register page in another browser (i'm using firefox container ) and create an another account using the same email with \u0023 at the end (victim@test.com\u0023) with different password( i'm using burpsuite to edit the email).

### Impact:
This vulnerability allows an attacker to take over any account on the website, without requiring any knowledge of the account's password. By adding `\u0023` at the end of an email address during the registration process, the attacker can register a new account with the same email address as an existing user, but with a different password. This grants the attacker full access to the victim's account and any associated data.
