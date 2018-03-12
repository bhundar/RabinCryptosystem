# RabinCryptosystem
The Rabin Cryptosystem is a cryptography technique that uses asymmetry. This system was published in 1979 as one of the very first asymmetric cryptography system.

# How it works
# 1. Generating the Key
1. Choose two distince prime p and q ((p ≡ q ≡ 3 mod 4) can be chosen to simply computing square roots).
2. Let the Public Key n, be p * q.
3. The primes p and q are the Private Key.

# 2. Encryption
The public key is used for Encryption:

1. The plaintext, P is represented as P = {0,...,n-1} and let m ∈ P.
2. The ciphertext, c is computed as follows: c = m^2 mod n.

# 3. Decryption
The private key is used for Decryption:

1. The plaintext is m ∈ {0,...,n-1} and m^2 ≡ c mod n.
2. The Chinese Remainder Theorem is used to find m:
    m(sub)p = c^(1/2) mod p     and     m(sub)q = c^(1.2) mod q
3. Further, by applying the Extended Euclidean Algorithm we need to find y(sub)p and y(sub)q such that:
   y(sub)p * p + y(sub)q * q = 1
4. The 4 roots calculated are +r,-r,+s and -s such that:
   +r = (y(subp) * p * m(sub)q + y(sub)q * q * m(sub)p) mod n
   -r = n - r
   +s = (y(subp) * p * m(sub)q - y(sub)q * q * m(sub)p) mod n
   -s = n - s
One of these roots above mod n is the plaintext m.

