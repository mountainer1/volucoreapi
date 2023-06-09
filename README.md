# 1. VoluCore
VoluCore is a main component of Volumetres.
The VoluCore provides an API that handles the interaction of the frontend with the server.
# 2. API Reference
### 2.1 General Informations
- The API is binded on 127.0.0.1:9890, so the API is only reachable from the Server directly.
### 2.2 Endpoints

#### POST
- /addfwrule

This Endpoint is used to add a new Firewall rule. 
```
# Example cURL
curl -X POST -d '{"saddr":"1.2.3.4", "dport":"1337", "protocol":"tcp", "policy":"DROP"}' http://localhost:9890/addfwrule
```

#### DELETE 
- /delfwrule

This Endpoint is used to remove a Firewall rule. 
```
# Example cURL
curl -X DELETE -d '{"saddr":"1.2.3.4", "dport":"1337", "protocol":"tcp", "policy":"DROP"}' http://localhost:9890/delfwrule
```

#### GET
- /getfwrules

This Endpoint is used to get all Firewall rules.
```
# Example cURL
curl -X GET http://localhost:9890/getfwrules
```

- /getload

This Endpoint is used to get all Informations about the Server.
```
# Example cURL
curl -X GET -d '{"show":"["cpu", "memory", "disk", "processes"]"}' http://localhost:9890/getload
# Example cURL
curl -X GET http://localhost:9890/getload
```

# SSL
As this is the Core API running only locally on the System, there is no Support for SSL/TLS.