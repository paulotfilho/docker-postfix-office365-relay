# docker-postfix-office365-relay
A docker image that uses postfix as a relay through office365. Useful to link to other images. Forked from LyleScott's docker-postfix-gmail-relay.


## Configurables

```
SYSTEM_TIMEZONE = UTC or America/New_York
MYNETWORKS = "10.0.0.0/8 192.168.0.0/16 172.0.0.0/8"
EMAIL = your domain
EMAILPASS = password (is turned into a hash and this env variable is removed at boot)
```

## Example

```bash
docker run -i -t --rm \                                                        
    --name office365relay \
    -p 9025:25 \
    -e SYSTEM_TIMEZONE="America/New_York" \
    -e MYNETWORKS="10.0.0.0/8 192.168.0.0/16 172.0.0.0/8" \                    
    -e EMAIL="YOUR_EMAIL@example.com" \
    -e EMAILPASS="your_password" \
    postfix-office365-relay
```

