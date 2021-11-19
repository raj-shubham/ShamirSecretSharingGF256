# Shamir's secret sharing scheme in Go

This implementation of Shamir's secret sharing scheme uses finite field GF256 which contains 256 elements. This field is especially suitable for efficient field operations. GF256 is a popular finite field choice for working on bytes of data. It is also used in the implementation of AES due to its efficient operations which is also a reason for not using Z_p field.

## Finite field addition 

In the field GF256, addition of two elements is equal to xor operation.

## Finite field multiplication
The traditional way for multiplying GF256 elements requires multiplying the encoded polynomials and then taking the modulus operation with an irrreducible polynomial. To optimize this process, we use lookup tables for log and antilog values as used in popular AES implementation which uses GF256 field and works on bytes of data. The lookup table can be found in popular implementations of Galois Field 256.

## Finite field division
The traditional way for dividing GF256 elements requires multiplicative inverses using the encoded polynomials and then extended euclidean algorithm with an irrreducible polynomial. To optimize this process, we use lookup  tables for log and antilog values as used in popular AES implementation which uses GF256 field and works on bytes of data. The lookup table can be found in popular implementations of Galois Field 256.

## Golang
Version - go version go1.17.3 linux/amd64

## modules
### "fmt" - i/o
### "crypto/rand" - for secure random byte generation
### "crypto/subtle" - for timing attacks

## Execution
### step 1 : go build shamirSecretSharing.go // this creates an executable named shamirSecretSharing
### step 2 : ./shamirSecretSharing
