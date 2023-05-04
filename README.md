# droneci-aqua
Sample test integration Drone CI with Aqua

## Documentation

Basic parameter is 
```
docker run -v /var/run/docker.sock:/var/run/docker.sock registry.aquasec.com/scanner:2022.4 scan -H $aquaGW  -A $aquaToken  --registry "$regDomain" $imageName 
```
where 

- $aquaGW = aqua gateway url
- $aquaToken = aqua token
- $regDomain = Registry ex "Docker Hub" 
- $imageName = image name with tag ex nginx:lastest

when using local image, use parameter  --local imageName:tag
example
```
docker run -v /var/run/docker.sock:/var/run/docker.sock registry.aquasec.com/scanner:2022.4 scan -H $aquaGW  -A $aquaToken  --local imageName:tag
```

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

full documentation please refer to offcial aqua docs
[aquasec.com](https://support.aquasec.com/support/solutions/articles/16000120206-scanner-command-line-interface)
