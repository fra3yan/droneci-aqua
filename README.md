# droneci-aqua
Sample test integration Drone CI with Aqua

## Documentation

Basic parameter is 
```
docker run -v /var/run/docker.sock:/var/run/docker.sock registry.aquasec.com/scanner:2022.4 scan -H $aquaGW  -A $aquaToken  --registry "$regDomain" $imageName  docker:dind
```
where 

- $aquaGW = aqua gateway url
- $aquaToken = aqua token
- $regDomain = Registry ex hub.docker.com
- $imageName = image name with tag ex nginx:lastest

For security purpose please use secret in drone UI.
example parameter for get secret variable

```
  environment:
    regUser:
      from_secret: regUser
    regPass:
      from_secret: regPass
    aquaGW:
      from_secret: aquaGW
    aquaToken:
      from_secret: aquaToken
```

