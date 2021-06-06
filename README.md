# zero-knowledge-proof

ZKP implementation

### Theory

Alice knows the discrete logarithm of a given value as X in a known cyclic group Z, where X can be used as the proof of identity of Alice.
To show the proof that Alice has knowledge of X to Bob, Alice has to implement a honor process multiple times which will assist Bob to understand Alice has knowledge of X without actually learning the value of X.

### The handshake process

The handshake process decides the common parameters used in the discrete logarithmatic search, ie the Generator (g), modulus (p).

Assume, the generator (g) is 2 and the modulus (p) is 7

Alice picks a random number X, (proof of identity). g^X mod p gives Y and this value of Y is shared with Bob.

### The honor process

The honor process decides how much Bob can trust Alice on the proof of knowledge, by repeatedly checking Alice's capability to ensure the authenticity of the answer made to the request by Bob

The each round of the process start by,

- Alice selecting a random number R, and calculates a C = g^R mod p and passes the value of C to Bob
- After recieving the value of C, Bob proceeds to request Alice proof by disclosure of either R or the computation `(X+R) mod (p-1)`
