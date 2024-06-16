# How To Run
## 1. Download CouchDB From CouchDB Website
## 2. Setup local.ini File
``` 
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
## 3. Change the password in index into your CouchDB password
## 4. Run the code
``python -m http.server 8000``

