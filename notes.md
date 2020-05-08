Authentication (AuthN) === Who are you?
Authorization (AuthZ) === What do you want?

## JSON Web Token

header.payload.signature

## Header

base64({
algorithm: "HS256",
type: "JWT"
})

## Payload

base64({
membershipId: "123456",
accessLevel: "unlimited"
})

## Signature

hash(header + payload + secretString)

## JWT Auth Flow

- Client sends credentials to server (Login)
- Server verifies credentials (look up user, check password hash)
- Server creates a JWT for the client
- Server sends back the JWT as a header
- Client stores the JWT in local storage
- Client sends JWT on every subsequent request
- Server verifies the JWT is valid by checking the signature (no state required)
- Server provides access to the resource
