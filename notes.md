# 036

create enriroment variables

```dockerfile
ENV API_URL=https://api.myapp.com/
```

print api url

```bash
printenv
```

```bash
printenv API_URL
```

```bash
echo $API__URL
```

# 037 exposing ports

# 038 setting the user

make a group and a user with the primary gruop
app app is the standarts in linux for docker shit

```sh
addgroup app
adduser -S -G app app
```

check is the app user does have the app group

```sh
groups app
```

```sh
addgroup fefe && adduser -S -G fefe fefe
```

```sh
whoami
```

# 039 defining entrypoints
