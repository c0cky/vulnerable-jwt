# Camron and Jareds Super Awesome Security project

This repo contains a vulnerable API that examples how the `alg` header needs to be deprecated.

## Usage

1. Clone the repo
2. Install dependencies: `npm install`
3. Start the server: `node index.js`
4. Add your own mongodb server
5. Create sample user by visiting: `http://localhost:8080/setup`

## vulnerable

The way this application examples the vulnerability of the `alg` header is that by going to `http://localhost:8080/api/authenticatedbad` the server creates a token that is signed with the public key from the server but with `HMAC` as the `alg` not `RSA`, if the server is expecting a `RSA` and receives this token and validates it even though it is forged with the public key.
