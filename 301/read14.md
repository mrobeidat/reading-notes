>> What is Auth?

### OAuth is an authentication protocol that allows you to approve one application interacting with another on your behalf without giving away your password.

>> An example of Auth: 

### The simplest example of OAuth is when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you, and the website you were originally connecting to logs you on itself afterward using permission gained from the second website.

>> How does OAuth work? What are the steps that it takes to authenticate the user?

1. The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.
2. The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.
3. The first site gives this token and secret to the initiating user’s client software.
4. The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).
5. If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the
6. authorization transaction to the second website.
7. The user approves (or their software silently approves) a particular transaction type at the first website.
8. The user is given an approved access token (notice it’s no longer a request token).
9. The user gives the approved access token to the first website.
10.The first website gives the access token to the second website as proof of authentication on behalf of the user.
11.The second website lets the first website access their site on behalf of the user.
12.The user sees a successfully completed transaction occurring.

>> What is OpenID?

### OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans.

>> What is the difference between authorization and authentication?

### In simple terms, authentication is the process of verifying who a user is, while authorization is the process of verifying what they have access to.

>> What is Authorization Code Flow?

### the Authorization Code Flow, which exchanges an Authorization Code for a token.

>> What is Device Authorization Flow?

### instructs the user to review the authorization request on a secondary device

>> What is Resource Owner Password Flow?

### The Resource Owner Password Credentials flow allows exchanging the username and password of a user for an access token
