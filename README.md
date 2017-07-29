# Docker

## Usage
```bash
./configure
make && make install
```
```fish
./configure
make; and make install
```

## Test 
`http://localhost:80`

## Other
```bash
./configure --wwwroot ~/wwwroot \
--mysqlpassword 123456 \
--serverport 8080
make restart
make stop
make clean
```