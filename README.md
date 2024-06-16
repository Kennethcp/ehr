# How To Run

This guide provides step-by-step instructions for downloading and setting up CouchDB. Follow these instructions to get your CouchDB server up and running.

## 1. Download CouchDB

First, download CouchDB from the [CouchDB Website](https://couchdb.apache.org/).

## 2. Setup `local.ini` File

Edit the `local.ini` file with the following configuration:

```ini
[couchdb]
;max_document_size = 4294967296 ; bytes
;os_process_timeout = 5000

[chttpd]
port = 5984
bind_address = 0.0.0.0

; Options for the MochiWeb HTTP server.
;server_options = [{backlog, 128}, {acceptor_pool_size, 16}]
;socket_options = [{sndbuf, 262144}, {nodelay, true}]

[httpd]
enable_cors = true
WWW-Authenticate = Basic realm="administrator"
;config_whitelist = [{httpd,config_whitelist}, {log,level}, {etc,etc}]

[ssl]
;enable = true
;cert_file = /full/path/to/server_cert.pem
;key_file = /full/path/to/server_key.pem
;password = somepassword
;verify_ssl_certificates = false
;fail_if_no_peer_cert = false
;cacert_file = /full/path/to/cacertf
;verify_fun = {Module, VerifyFun}
;ssl_certificate_max_depth = 1
;secure_renegotiate = true
;ciphers = ["ECDHE-ECDSA-AES128-SHA256", "ECDHE-ECDSA-AES128-SHA"]
;tls_versions = [tlsv1, 'tlsv1.1', 'tlsv1.2']

[vhosts]
;example.com = /database/

[admins]
admin = (your CouchDB password)

[cors]
credentials = true
origins = *
headers = accept, authorization, content-type, origin, referer
methods = GET, PUT, POST, HEAD, DELETE
```
Don't forget to replace (your CouchDB password) in the [admins] sections with your actual CouchDB password.

## 3. Update Your index.html
Replace the PASSWORD into your CouchDB password
Replace IPADDRESS into your IP Address. You can check it by running ipconfig in cmd (if in windows)

## 4. Run The Code
Start a simple HTTP server to run your CouchDB setup. Use the following command:
```
python -m http.server 8000
```

## 5. Open the page
Search localhost:8000/index.html in your browser
