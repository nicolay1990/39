```
#CA
openssl genrsa -out rootCA.key 2048
openssl req -x509 -new -key rootCA.key -days 3650 -out rootCA.crt

#Cert
openssl genrsa -out server101.mycloud.key 2048
openssl req -new -key server101.mycloud.key -out server101.mycloud.csr -addext "subjectAltName = DNS:core.wsr"
openssl x509 -req -in server101.mycloud.csr -CA rootCA.crt -CAkey rootCA.key -CAcreateserial -out server101.mycloud.crt -days 730


#extfile (-)
basicConstraints=CA:FALSE
extendedKeyUsage=serverAuth
subjectAltName=DNS:www.demo.wsr
```