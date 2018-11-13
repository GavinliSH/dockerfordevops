### Build
```
docker build -t winjen .
```
### Run
```
docker run -id -p 8080:8080 -p 50000:50000 --name win-jenkins winjen
```