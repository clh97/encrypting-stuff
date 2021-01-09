# encrypting-stuff
OpenSSL simple way of encrypting files

---

## generates private key
`openssl genrsa -des3 -out private.key 4096``
## generates public key from private key
`openssl rsa -in private.key -pubout -out public.key`
## creating a really secret file
`nvim secret.txt`
## encrypts the file using public key`
`openssl rsautl -encrypt -pubin -inkey public.key -in secret.txt -out encrypted.txt`
## such security, much encryption!!1 wow
`cat encrypted.txt`
## decrypts the encrypted file using private key
`openssl rsautl -decrypt -inkey private.key -in encrypted.txt -out plain.txt`
## plain.txt == secret.txt
`cat plain.txt`
