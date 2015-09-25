# openssl role

### variables

```yaml
openssl_certificates:
  - name: foo
    key_path: /etc/apache2/   # optional
    cert_path: /etc/apache2/  # optional
    merge: true               # merge key and certificate into a unique file?
    chain: true               # merge CA chain, key and certificate into a unique file?
    owner: rails              # optional
    group: rails              # optional
    cert: |+
      -----BEGIN CERTIFICATE-----
      -----END CERTIFICATE-----
    key: |+
      -----BEGIN RSA PRIVATE KEY-----
      -----END RSA PRIVATE KEY-----
  - name: bar
    chain: true               # merge CA chain and certificate into a unique file?
    cert: |+
      -----BEGIN CERTIFICATE-----
      -----END CERTIFICATE-----
    key: |+
      -----BEGIN RSA PRIVATE KEY-----
      -----END RSA PRIVATE KEY-----
```

certificate authority configuration:
```yaml
openssl_ca:
  - name: comodo
    path: /etc/apache2       # optional
    owner: rails             # optional
    group: rails             # optional
    ca: |+
      -----BEGIN CERTIFICATE-----
      -----END CERTIFICATE-----
  - name: comodo2
    ca: |+
      -----BEGIN CERTIFICATE-----
      -----END CERTIFICATE-----
```
