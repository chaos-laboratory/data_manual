# Request for SSL Certificate from Princeton

1. For generating the CSR for the database please refer to [these instructions](https://chenkianwee.github.io/masa3db/docs/040/049ssl_cert.html).
2. Go to the OIT helpdesk webpage for requesting [SSL certificate](https://princeton.service-now.com/service?id=kb_article&sys_id=b22a27064f9ca20018ddd48e5210c777). Then fill in the [form](https://princeton.service-now.com/service?sys_id=c85dafbd4f752e0018ddd48e5210c7e4&id=sc_cat_item&table=sc_cat_item)
3. You will receive several certificates. First the domain certificate. Cut and paste them like this in a .crt file
    ```
    -----BEGIN CERTIFICATE-----
    (encoded stuff)
    -----END CERTIFICATE-----
    ```
4. The root certificate. Cut and paste them like this in a .crt file
    ```
    -----BEGIN CERTIFICATE-----
    (encoded stuff)
    -----END CERTIFICATE-----
    ```
5. The intermediate certificate. Cut and paste them like this in a .crt file
    ```
    -----BEGIN CERTIFICATE-----
    (encoded stuff)
    -----END CERTIFICATE-----
    ```
    ```
    !!! Make sure there are no spaces at all,
    no empty lines no spaces any spaces will make the file invalid !!!
    ```

6. Copy the certificate into the container running Frost-server, then follow instructions in step 1.
