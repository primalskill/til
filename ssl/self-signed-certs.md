# Self-Signed Certificates for Development

- Create a root CA which is trusted locally. This needs to be created once.
- Use that CA to sign project specific development certificates. This needs to be created on a per project basis.


## Generate a CA

```shell
# First generate a key
openssl genrsa -des3 -out dev_ca.key 2048

# Generate the certificate
openssl req -x509 --new -nodes -key dev_ca.key -sha256 -days 1825 -out dev_ca.pem -subj "/C=/ST=/L=/O=/CN=DevelopmentCA"
```

## Trust the CA

Manually, on macOS use the KeyChain app to import the CA and trust it or use the devcert tool to do it automatically (See Refs below).




## Generate a Project Certificate

```shell
# Generate a key
openssl genrsa -out my_project.key 2048

# Generate a certificate signing request (CSR)
openssl req -new -key my_project.key -subj "/C=/ST=/L=/O=/CN=MyProject" -out my_project.csr

# Create an EXT file for the certificate
cat > my_project.ext << EOF
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = critical, keyAgreement, digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
extendedKeyUsage = serverAuth
subjectAltName = @alt_names
[alt_names]
DNS.1 = my_project.local
EOF

# Finally, generate the certificate
openssl x509 -req -in my_project.csr -CA dev_ca.pem -CAkey dev_ca.key -CAcreateserial -out my_project.crt -days 200 -sha256 -extfile my_project.ext
```

------------

**Refs**

- Created a CLI tool for easily generating certificates: [github.com/primalskill/devcert](https://github.com/primalskill/devcert)
