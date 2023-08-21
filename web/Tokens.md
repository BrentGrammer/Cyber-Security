# TOKENS

## JWT

- https://stackoverflow.com/questions/38018469/how-exactly-does-json-web-token-jwt-reduce-the-man-in-the-loop-attack
- **The key concept of this stratagem is very much that of POSSESSION. "You have it or you don't," and anyone who DOES "have it" is going to be recognized. That's simply how the design was done.**
- Can be snatched in man in the middle attacks
  - at minimum you need SSL/HTTPS to encrypt tokens to reduce risk.
    - even then, they can be snatched: SSL traffic can still be sniffed and tokens can be stolen. There are no real solutions to that in JWT. Expiration doesn't help because the attacked can probably steal the fresh token. I've seen posts from auth0 or oauth.io about using AI to determine unusual token usage in APIs. The most promising solution to replay and mitm is a concept called "token binding", and it is already used in the industry where extra security is needed - like banking. It binds the token to the public/private key on the browser. PingIdentity is one provider.
