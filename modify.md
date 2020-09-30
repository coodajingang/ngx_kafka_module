## Modify 
* support GET method , when get , will write kafka like this:   NG-GET || METHOD || REQUEST-LINE || ARGS || URI || HOST|| USER-AGENT || REQUEST-TIME||  
* support sasl parameters 

### example  
    kafka;
    kafka_broker_list x.x.x.x:p x.x.x.x:p ;
    kafka_security_protocol sasl_plaintext;
    kafka_sasl_mechanisms SCRAM-SHA-256;
    kafka_sasl_username name;
    kafka_sasl_password pwd;
    kafka_sasl_switch on/off;

### build cmd 
#### librdkafka 
 use version of 1.2.2 ,  becourse Kafka version is 2.0 . 

 ./configure --enable-sasl --enable-lz4 
 make 
 make install  

 #### nginx  
 use version 1.14.0  

 ./configure --add-dynamic-module=/root/ngx_kafka_module --prefix=/usr/local/nginx --with-cc-opt=-O2 --with-http_stub_status_module --with-http_ssl_module --with-http_gzip_static_module --with-stream --with-http_flv_module --with-http_realip_module --with-debug 
 make modules  

 